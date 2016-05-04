# MetamodelAdaptor
Automatic creation of an ADAPTER as part of the chain of transformations process.


All is contained in the folder Adaptor.
There's an hierarchical structure of the subfolders:

- emfCompare:
	This folder contains the EMFCompare metamodel and the comparison models obtained
	from the metamodels defined in the project.
	All the stuff regarding EMFCompare and comparison results have to be here.
- epsilon
	It contains the EGL engine that creates the tranformation based on the 
	difference model. It contains also the created ETL transformation code as the
	result of the analysis of the differences.
- metamodel
	It contains the metamodel defined and compared. To be correctly assumed by EMFCompare
	they have to be named: 
		<name>Right.ecore for the source
		<name>Left.ecore for the evoluted one.
	Before the extension they could be indexed by integers if there are many version of them.
	Example:
		trialRight1.ecore (first version source)
		trialRight2.ecore (second version source)
		trialLeft.ecore (unique evoluted one)
- model
	It contains the models defined as implementation of the metamodels above.
	Here will be created the evoluted models by the ETL code.

Usage: (with configuration, not plugin)

	To create automatically the ETL transformation:

		1) Launch the "adaptor.egl" in the "epsilon" folder, with the correct
			difference model aliased "Comp".

		2) Launch the built ETL transformation onto all the wanted source models,
			with the source metamodel aliased "Input" and the output one
			aliased "Output". Check the names of the input and output models
			in the configuration.


Have Fun!!