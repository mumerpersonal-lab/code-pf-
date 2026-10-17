<h1>PF LAB 07 </h1>
<h2>Question no 1</h2>
#include<stdio.h><br>
int main()<br>
{ int mat[3][3]={{4,23,3},{4,7,6},{7,11,9}};<br>
  int transpose[3][3];<br>
  int co_factors[3][3];<br>
  int ADJ[3][3];<br>
  float INV[3][3];<br>
  int i=0,j=0,k=0,l=0;<br>
  float det=0;<br>
  //TRANSPOSE<br>
  for(i=0;i<3;i++)<br>
  {for(j=0;j<3;j++)<br>
  {transpose[i][j]=mat[j][i];}<br>
  }<br>
  printf("TRANSPOSE\n");<br>
  for(i=0;i<3;i++)<br>
  {for(j=0;j<3;j++)<br>
  {printf("%d ",transpose[i][j]);}<br>
  printf("\n");  <br>
  }<br>
  //DETERMINANT<br>
  for(i=0;i<3;i++)<br>                                       
  {  float m_d=1,a_d=1;<br>
   for(j=0;j<3;j++)<br>
   {m_d*=mat[j][(i+j)%3];<br>
    a_d*=mat[j][(i-j+3)%3];<br>
   }<br>
    det+=m_d-a_d;<br>
  }<br>
  printf("DETERMINANT\n%f\n",det);<br>
  //CO-FACTORS<br>
  for(i=0;i<3;i++)<br>
  { for(j=0;j<3;j++)<br>
   {<br>
    int M[2][2];<br>
    int sr=0;<br>
    for(k=0;k<3;k++)<br>
    {if(k==i)<br>
	{continue;}<br>
	int sc=0;<br>
	for(l=0;l<3;l++)<br>
	{if(l==j)<br>
	{continue;}<br>
	 M[sr][sc]=mat[k][l]; sc++;<br>
	}<br>
	sr++;<br>
	}<br>
   int det2=M[0][0]*M[1][1]-M[0][1]*M[1][0];<br>
   if((i+j)%2!=0){det2=det2*(-1);}<br>
   else{det2=det2;}<br>
   co_factors[i][j]=det2;<br>
   }<br>
  }<br>
  printf("CO-FACTORS\n");<br>
  for(i=0;i<3;i++)<br>
  {for(j=0;j<3;j++)<br>
  {printf("%d ",co_factors[i][j]);}<br>
  printf("\n");<br>
  }<br>
  //ADJOINT<br>
   for(i=0;i<3;i++)<br>
  {for(j=0;j<3;j++)<br>
  {ADJ[j][i]=co_factors[i][j];}<br>
  }<br>
  printf("ADJOINT\n");<br>
  for(i=0;i<3;i++)<br>
  {for(j=0;j<3;j++)<br>
  {printf("%d ",ADJ[i][j]);}<br>
  printf("\n");  <br>
  }<br>
  //INVERSE<br>
  if(det==0){printf("INVERSE IS NOT POSSIBLE :/");}<br>
   else<br>
   {for(i=0;i<3;i++)<br>
       {for(j=0;j<3;j++)<br>
        {INV[i][j]=(float)(ADJ[i][j])/det;}<br>
     printf("INVERSE\n");<br>
      for(i=0;i<3;i++)<br>
       {for(j=0;j<3;j++)<br>
      {printf("%.2f ",INV[i][j]);}<br>
      printf("\n");<br>
        }<br>
       }<br>
   }<br>
   
	return 0;
}<br>
<img width="408" height="486" alt="image" src="https://github.com/user-attachments/assets/0896f34a-5d80-43cf-9b13-352b86696d82" /><br>


<h2>Question no 2</h2><br>
#include<stdio.h><br>
int main()<br>
{ int i=0,j=0,r=0,c=0,r2=0,c2=0,square=0,zero=0,identity=0,diagonal=0,<br>
      scalar=0,utri=0,ltri=0,skew=0,symm=0,sing=0,nsing=0,<br>
      row=0,column=0,null=0,idem=0,nilpo=0;  <br>
  char n;<br>
  printf("Do You want to compare two matrices?\nY/N ");<br>
  scanf("%c",&n);<br>
  if(n=='Y'||n=='y')<br>
  {<br>
  printf("Enter number of rows of  your first matrix(max 2): ");<br>
  scanf("%d",&r);<br>
  printf("Enter number of columns of your first matrix(max 2): ");<br>
  scanf("%d",&c);<br>
  printf("Enter number of rows of  your second matrix(max 2): ");<br>
  scanf("%d",&r2);<br>
  printf("Enter number of columns of your second matrix(max 2): ");<br>
  scanf("%d",&c2);<br>
  int mat1[r][c],mat2[r2][c2];<br>
	
  for(i=0;i<r ;i++)   <br>
   { for(j=0;j<c;j++) <br>   
     { printf("Enter mat1[%d][%d]: ",i,j);<br>
       scanf(" %d",&mat1[i][j]);<br>
       printf("\n");<br>
     }<br>
   }   <br>
   for(i=0;i<r2;i++)   <br>
   { for(j=0;j<c2;j++)<br>
     { printf("Enter mat2[%d][%d]: ",i,j);<br>
       scanf(" %d",&mat2[i][j]);<br>
       printf("\n");<br>
     }<br>
   }<br>
  if(r==r2&&c==c2)<br>
   {for(i=0;i<r;i++)<br>
    { for(j=0;j<c;j++)<br>
      {if(mat1[i][j]==mat2[i][j])<br>
       {continue;}<br>
       else{printf("Not Equal matrices.");return 0;}<br>
     }<br>
    }printf("Equal matrices.");return 0;<br>
   }<br>
   else{printf("Not equal Order.");return 0;}<br>
 }<br>
 else<br>
 {printf("Enter number of rows of  your  matrix(max 2): ");<br>
  scanf("%d",&r);<br>
  printf("Enter number of columns of your matrix(max 2): ");<br>
  scanf("%d",&c);<br>
  int mat1[r][c];<br>
   for(i=0;i<r;i++)<br>
   { for(j=0;j<c;j++)<br>
     { printf("Enter mat1[%d][%d]: ",i,j);<br>
       scanf(" %d",&mat1[i][j]);<br>
       printf("\n");<br>
     }<br>
   }   <br>
    if(c==0){row=1;}<br>
    if(r==0){column=1;}<br>
    if(r==c){square=1;}<br>
    zero=1;<br>
    null=1;<br>
     for(i=0;i<r;i++)<br>
   { for(j=0;j<c;j++)<br>
     {if (mat1[i][j]==0){continue;}<br>
      else{zero=0;null=0;}<br>
     }<br>
   }   <br>
   identity=1;<br>
     for(i=0;i<r;i++)<br>
   { for(j=0;j<c;j++)<br>
     {if ((i==j&&mat1[i][j]!=1)||(i!=j&&mat1[i][j]!=0)){identity=0;}<br>
     }<br>
   }   <br>
   diagonal=1;<br>
     for(i=0;i<r;i++)<br>
   { for(j=0;j<c;j++)<br>
     {if (i!=j&&mat1[i][j]!=0){diagonal=0;}<br>
     }<br>
   }   <br>
   scalar=1;<br>
     for(i=0;i<r;i++)<br>
   { for(j=0;j<c;j++)<br>
     {if (i!=j&&mat1[i][j]!=0){scalar=0;}<br>
     }<br>
   }   <br>
   if (diagonal && r > 0) {<br>
   int val = mat1[0][0];<br>
   scalar = 1;<br>
   for (i = 0; i < r; i++) {<br>
   if (mat1[i][i] != val) scalar = 0;<br>
    }<br>
   }<br>
    utri = 1;<br>
    for (i = 0; i < r; i++) {<br>
    for (j = 0; j < c; j++) {<br>
    if (i > j && mat1[i][j] != 0) utri = 0;<br>
     }<br>
    }<br>
    ltri = 1;<br>
    for (i = 0; i < r; i++) {<br>
    for (j = 0; j < c; j++) {<br>
    if (i < j && mat1[i][j] != 0) ltri = 0;<br>
     }<br>
    }<br>
    symm = 1;<br>
    for (i = 0; i < r; i++) {<br>
    for (j = 0; j < c; j++) {<br>
    if (mat1[i][j] != mat1[j][i]) symm = 0;<br>
    }<br>
    }<br>
   symm = 1;<br>
   for (i = 0; i < r; i++) {<br>
   for (j = 0; j < c; j++) {<br>
   if (mat1[i][j] != -mat1[j][i]) symm = 0;<br>
   }<br>
   }<br>
   int det = 0;<br>
   if (r == 1) det = mat1[0][0];<br>
   else if (r == 2) det = mat1[0][0] * mat1[1][1] - mat1[0][1] * mat1[1][0];<br>
   if (det == 0) sing = 1;<br>
   else nsing = 1;<br>
   int mat2[r][c];<br>
   for(i=0;i<r;i++)<br>
   { for(j=0;j<c;j++){mat2[i][j]=mat1[i][j];}<br>
   }<br>
   if (r == 2) {<br>
   int m2[2][2] = {{0, 0}, {0, 0}};<br>
   int k=0;<br>
   for (i = 0; i < 2; i++) {<br>
   for (j = 0; j < 2; j++) {<br>
   for (k = 0; k < 2; k++) {<br>
   m2[i][j] += mat1[i][k] * mat1[k][j];<br>
     }<br>
    }<br>
   }<br>

   idem = 1;<br>
   nilpo = 1;<br>
   for (i = 0; i < 2; i++) {<br>
   for (j = 0; j < 2; j++) {<br>
   if (m2[i][j] != mat1[i][j]) {idem = 0;}<br>
   if (m2[i][j] != 0) {nilpo = 0;}<br>
    }<br>
   }<br>
  }<br>
 }   <br>
 printf("Information about your matrix :\n");<br>
 if(r==1){printf("ROW MATRIX\n");}<br>
 if(c==1){printf("COULUMN MATRIX\n");}<br>
 if(square==1){printf("SQUARE MATRIX\n");}<br>
 else{printf("RECTANGLE MATRIX\n");}<br>
 if(null==1){printf("NULL MATRIX\n");}<br>
 if(zero==1){printf("ZERO MATRIX\n");}<br>
 if(identity==1){printf("IDENTITY MATRIX\n");}<br>
 if(diagonal==1){printf("DIAGONAL MATRIX\n");}<br>
 if(scalar==1){printf("SCALAR MATRIX\n");}<br>
 if(utri==1){printf("UPPER TRIANGULAR MATRIX\n");}<br>
 else{printf("LOWER TRIANGULAR MATRIX\n");}<br>
 if(symm==1){printf("SYMMETRIC MATRIX\n");}<br>
 else{printf("SKEW SYMMETRIC MATRIX\n");}<br>
 if(sing==1){printf("SINGULAR MATRIX\n");}<br>
 else{printf("NON SINGULAR MATRIX\n");}<br>
 if(idem==1){printf("IDEMPOTENT MATRIX\n");}<br>
 if(nilpo==1){printf("NILPOTENT MATRIX\n");} <br>
 <br>
  return 0;<br>
}<br>
<img width="473" height="540" alt="image" src="https://github.com/user-attachments/assets/5789f819-47b6-487c-916b-4cbdf73fc194" /><br>





