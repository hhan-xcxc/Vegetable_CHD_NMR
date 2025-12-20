# Purpose: This script generates simulated data for demonstration purposes only.

set.seed(123)

vegs      <- paste0("veg", 1:21)         # 21 vegetables
othfoods  <- paste0("otherFOOD", 1:45)   # 45 food items (except for vegetables)
features  <- paste0("feature", 1:589)    # 589 nmr features

n_row <- 20 

# intake data >=0
prop_zero_veg <- runif(1, min = 0.2, max = 0.5)
prop_zero_oth <- runif(1, min = 0, max = 0.6)

veg_mat <- matrix(
  runif(n_row * length(vegs), min = 0, max = 50),
  nrow = n_row,
  dimnames = list(NULL, vegs)
)

othfoods_mat <- matrix(
  runif(n_row * length(othfoods), min = 0, max = 100),
  nrow = n_row,
  dimnames = list(NULL, othfoods)
)

n_veg <- length(veg_mat)  # 元素总数
idx_zero_veg <- sample(
  1:n_veg,
  size = round(prop_zero_veg * n_veg),
  replace = FALSE
)
veg_mat[idx_zero_veg] <- 0

n_oth <- length(othfoods_mat)
idx_zero_oth <- sample(
  1:n_oth,
  size = round(prop_zero_oth * n_oth),
  replace = FALSE
)
othfoods_mat[idx_zero_oth] <- 0

feature_mat <- matrix(
  rnorm(n_row * length(features)),
  nrow = n_row,
  dimnames = list(NULL, features)
)

demo_data <- data.frame(
  demoID = 1:n_row,
  veg_mat,
  othfoods_mat,
  feature_mat,
  check.names = FALSE
)

dim(demo_data)  

write.csv(demo_data, file = "./demo_data.csv",row.names = FALSE)

# The 'demo_data' dataset shares the same structure as the main analysis dataset 'ana_wk2' and is used for demonstration only.

