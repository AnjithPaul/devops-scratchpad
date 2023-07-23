#devOps #architecture #architecturePatterns 

- [ ] system which produce and **process stream of data**
- [ ] Components
	- [ ] **filter**
		- [ ] each processing step is enclosed within a filter
	- [ ] **pipes**
		- [ ] data to be processed is passed through pipes
- [ ] Source->pipe 1->filter 1->pipe 2->filter 2-> ...->filter n-> Sink
- [ ] Advantages
	- [ ] System can be **extended** easily
- [ ] Disadvantages
	- [ ] Efficiency is limited by the slowest filter process
- [ ] Usage
	- [ ] Compilers
		- [ ] consecutive filters perform lexical analysis, parsing, etc
	- [ ] Workflows in bioinformatics