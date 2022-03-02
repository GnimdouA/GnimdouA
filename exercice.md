### Hi there 👋

# Exercice1.1

# 1.création des vecteur avec rep. créons le vecteur source sur lequel nous appliquerons la fonction rep 
#pour obtenir les résultats atendus il s'agit du vecteur contenant les chiffres 1 à 5
x <- c(1,2,3,4,5)
vect1 <- rep(x,times = 3) # pour avoir vect1 il faut répéter x 3 fois
vect2 <- rep(x,each = 3) # pour avoir vect2 il faut répéter chacun des éléments de x trois fois
vect3 <- rep(1:4, c(2,3,4,5)) # pour vect3 il faut repéter chacun des éléments i de (1,2,3,4)i+1 fois

# 2.création de vecteur avec la fonction paste
vec4 <- paste('A', paste(1:10, ')', sep = ''),sep = '')

# 3.position de q et création du vecteur vec5 = (a1,a2,...qposition_de_q)
letters
y = which(letters == "q") # renvoie un vecteur avec l’index (ou les index) de l’élément q
vec5 <- paste(letters[1:y],1:y, sep ='' )


# Exercice_1.2

#1. création de vec1 et calcul de la moyenne et de la variance
set.seed(007)
vec1 <- runif(100,0,7)
moyenne <- mean(vec1)
variance <- var(vec1)

# 2.création de vec2, des valeurs mamquantes et recherche de leurs indices
vec2 <- vec1
set.seed(008)
vec2 <- replace(vec2,sample(1:100, size=10),NA)
indice_na = which(is.na(vec2)== TRUE)

# 3.calcul de la moyenne et de la variance de vec2 :
# sans prendre en compte les na
m_avec_na <- mean(vec2)


# Exercice_1.3

# 1.création de matrice
mat <- matrix(data = c(1,0,3,4,5,5,0,4,5,6,3,4,0,1,3,2),nrow = 4)
rownames(mat) = paste('Ligne', 1:4, sep = '-')
colnames(mat) = paste('Colone', 1:4, sep = ' ')

# 2.création de diag
diag <- c(mat[1,1], mat[2,2], mat[3,3], mat[4,4])

# 3.création d'une matrice contenant uniquement les 2 premières lignes de mat
mat_2 <- mat[paste('ligne', 1:2, sep = '-'),]

# 4.création d'une matrice contenant uniquement les 2 dernières colonnes de mat
mat_3 <- mat[,paste('colonne', 3:4, sep = ' ')]

# 5.création d'une matrice contenant toutes les colonnes de mat sauf la troisième
mat_4 <- mat[,c(1,2,4)]

# 6.calcul du determinant et de l'inverse de mat
det_mat <- det(mat) # déterminant
inv_mat <- solve(mat) # inverse
v_avec_na <- var(vec2)
# en prenant en compte les na
m_sans_na <- mean(vec2, na.rm = TRUE)
v_sans_na <- var(vec2, na.rm = TRUE)

# 4.création de vec3 et calcul de la moyenne et de la variance
vec3 <- vec2[!is.na(vec2)] # vec3 = ensemble des éléments de vec2 qui sont différents de na
moy <- mean(vec3)
vari <- var(vec3)

# 5.création de vec4 et calcul de la moyenne et de la variance
vec4 <- replace(vec2, indice_na, moy)
moy_4 <- mean(vec4)
vari_4 <- var(vec4)

# 6. création de vec5 et calcul de la moyenne et de la variance
vec5 <- replace(vec2,indice_na, rnorm(10,mean(vec3),sqrt(var(vec3))))
moy_5 <- mean(vec5)
vari_5 <- var(vec5)
moy_5
vari_5

# 7.création de vec6 et calcul de la moyenne et de la variance
vec6 <- replace(vec2,indice_na, runif(10,min(vec3),max(vec3)))
moy_6 <- mean(vec6)
vari_6 <- var(vec6)

# 8.création de vec7
vec7 <- replace(vec2,indice_na, sample(vec2[!is.na(vec2)], size=10, replace = TRUE))

-->
