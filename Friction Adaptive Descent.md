

Command to run single epoch (on cpu):

python ./jobs/job.py single_run exp_name ./experiments cpu MNIST fully_connected 64 ADAM 1 ./experiments/ADAM_defaults.json true

Command to run multiple epochs e.g. 5 (on cpu):

python ./jobs/job.py single_run exp_name ./experiments cpu MNIST fully_connected 64 ADAM 5 ./experiments/ADAM_defaults.json true

Command to run a single hyperparameter trial, 1 epoch, 1 repeat per trial, 1 job (on cpu)

python ./jobs/job.py hyperparam_search exp_name ./experiments cpu MNIST fully_connected 64 ADAM 1 ./experiments/ADAM_defaults.json true 1 1 train_loss 1

Command to run 3 hyperparameter trials, 3 epochs, 3 repeats per trial, 1 job (on cpu):

python ./jobs/job.py hyperparam_search exp_name ./experiments cpu MNIST fully_connected 64 ADAM 3 ./experiments/ADAM_defaults.json true 3 3 train_loss 1

Optuna with subsequent validation

python ./jobs/job.py hyperparam_search exp_name ./experiments cuda MNIST fully_connected 64 ADAM 1 ./experiments/ADAM_defaults.json true 2 2 train_loss 1 2 2 2


MNIST fully connected train_loss 
=========

python ./jobs/job.py hyperparam_search MNIST_fc_ADAM_train_loss ./experiments cuda MNIST fully_connected 64 ADAM 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_CADAM_train_loss ./experiments cuda MNIST fully_connected 64 CADAM 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_FADAM_train_loss ./experiments cuda MNIST fully_connected 64 FADAM 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_KFAD_train_loss ./experiments cuda MNIST fully_connected 64 KFAD 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_mSGD_train_loss ./experiments cuda MNIST fully_connected 64 mSGD 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_CUBIC_train_loss ./experiments cuda MNIST fully_connected 64 CUBIC 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_iKFAD_train_loss ./experiments cuda MNIST fully_connected 64 iKFAD 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

MNIST fully connected test_loss
=======

python ./jobs/job.py hyperparam_search MNIST_fc_ADAM_test_loss ./experiments cuda MNIST fully_connected 64 ADAM 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_CADAM_test_loss ./experiments cuda MNIST fully_connected 64 CADAM 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_FADAM_test_loss ./experiments cuda MNIST fully_connected 64 FADAM 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_KFAD_test_loss ./experiments cuda MNIST fully_connected 64 KFAD 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_mSGD_test_loss ./experiments cuda MNIST fully_connected 64 mSGD 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_CUBIC_test_loss ./experiments cuda MNIST fully_connected 64 CUBIC 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_fc_iKFAD_test_loss ./experiments cuda MNIST fully_connected 64 iKFAD 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

MNIST ResNet train_loss 
=========

python ./jobs/job.py hyperparam_search MNIST_resnet_ADAM_train_loss ./experiments cuda MNIST res_net 64 ADAM 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_CADAM_train_loss ./experiments cuda MNIST res_net 64 CADAM 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_FADAM_train_loss ./experiments cuda MNIST res_net 64 FADAM 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_KFAD_train_loss ./experiments cuda MNIST res_net 64 KFAD 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_mSGD_train_loss ./experiments cuda MNIST res_net 64 mSGD 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_CUBIC_train_loss ./experiments cuda MNIST res_net 64 CUBIC 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_iKFAD_train_loss ./experiments cuda MNIST res_net 64 iKFAD 50 ./experiments/ADAM_defaults.json false 200 3 train_loss -1 10 10 50

MNIST ResNet test_loss
=======

python ./jobs/job.py hyperparam_search MNIST_resnet_ADAM_test_loss ./experiments cuda MNIST res_net 64 ADAM 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_CADAM_test_loss ./experiments cuda MNIST res_net 64 CADAM 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_FADAM_test_loss ./experiments cuda MNIST res_net 64 FADAM 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_KFAD_test_loss ./experiments cuda MNIST res_net 64 KFAD 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_mSGD_test_loss ./experiments cuda MNIST res_net 64 mSGD 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_CUBIC_test_loss ./experiments cuda MNIST res_net 64 CUBIC 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50

python ./jobs/job.py hyperparam_search MNIST_resnet_iKFAD_test_loss ./experiments cuda MNIST res_net 64 iKFAD 50 ./experiments/ADAM_defaults.json false 200 3 test_loss -1 10 10 50
