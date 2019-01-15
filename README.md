# meditation_model
A Prims computational model of meditation and its transfer to a sustained attention task

This repository contains computational models of focused attention meditation and a sustained attention to response task (SART). They can be run in Prims (https://github.com/ntaatgen/ACTransfer), a general archictecture of human cognition. It is an extension/adaptation of ACT-R. The corresponding paper can be found here: https://pdfs.semanticscholar.org/870e/58eed0660de6ede3b635d833fc10949f1a48.pdf

The .pdf files are diagrams of the models.

There is a meditation model, simulating a simplified version of what possibly happens during focused attention meditation. Then there is multiple versions of the SART task model, which are needed to simulate transfer from the meditation task to the SART. The idea is to see what would happen if somone did the SART, then meditated for 18 hours and then did the SART again (and compare that to a control group).
The ".prims" files are the models that are read into Prims to be simulated. The ".bprims" files are alse read into Prims and contain information about the sequence and number of repetitions of simulations.

The transfer scenario proceeds as follows:
1. The "SARTtrain.prims" model is run to simulate the practice trials
2. The "SARTlater.prims" model is run to simulate the test trials. The operators from the first model are automatically transfered, therefore the second model has to be empty at first, as no new operators are learned in the practice phase (i.e. the operators of the test phase are identical to the practice phase).
3. There is a reset to flush the model and the operators
4. 18 hours of simulated meditation occurs
5. There is a reset to flush the model and the operators
6. The "SARTtrainTrans.prims" model is run to simulate the practice trials. This model contains new operators "learned" in meditation.
7. The "SARTlaterTrans.prims" model is run to simulate the test trials. The operators from the "SARTtrainTrans.prims" model are automatically transfered, therefore the second model also has the meditation operators.

The control scenario is the same but without the transfer of meditation operators.
