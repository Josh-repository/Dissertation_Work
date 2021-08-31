# Dissertation_Work
## Timeline
Implemetation of TTR actions in terms of finite state machine.

Date: 15-12-2020
1. Uploaded solution for zebra puzzle by making use of python.
3. Research work carried out on TTR 
2. Python sample code containing TTR. 

Date: 26/03/2021
1. Researched about Allen Relation, Monadic Second Order Logic and Transivity Table.
2. Uploaded "Allen_Relation[Future to Past] & [Past to Future]" and "Gap_Implementation" in jupyter notebook.

Date: 16/07/2021
1. Research work related to U,L,D construction based on conditions attached with events as it unfolds.
2. Uploaded "{U,L,D}_Automata_Construction" code.
3. Updated with tkinter on 16/08/2021. 

Date: 01/08/2021
1. Researched about Role of MSO in superposing automaton.
2. Uploaded "Superposing_Automata(over an alphabet of sets)".
3. Updated with tkinter on 16/08/2021.

Date: 16/08/2021.
1. Updated "Final_ProjectDemo" file consisting of colloborated codes of all previous work in addition to code for Projection via Allen Composition.


## Steps to run:

To run these programs, following steps should be followed - <br>
• Upgrade python version to the latest one(3.9.0)<br>
• Download dependencies using pip3 for -<br>
grphviz = 2.49.0
tkinter = 8.5 <br>
visual-automata = 1.1.1 <br>
Pillow = 8.3.1 <br>
pdf2image 1.16.0 <br>
• In the following file path : C:\Users\yourUser\Anaconda3\Lib\site-packages\visual_automata\fa\nfa.py <br>
At line 504 - 515 replace the code with the below code <br>
       
       for i in input_str:<br>
            status: bool = self.nfa.accepts_input(input_str=input_str)<br>
            status, taken_transitions_pairs = self._pathfinder(<br>
            input_str=input_str, status=status<br>
            )<br>    
And in the file path, C:\Users\yourUser\Anaconda3\Lib\site-packages\automata\fa\nfa.py <br>
change the line func _get_lambda_closure()  code to the following <br>
        stack = []<br>
        encountered_states = set()<br>
        stack.append(start_state)<br>

        while stack:<br>
            state = stack.pop()<br>
            if state not in encountered_states:<br>
                encountered_states.add(state)<br>
                try:<br>
                    if '' in self.transitions[state]:<br>
                        stack.extend(self.transitions[state][''])<br>
                except:<br>
                    continue<br>
        return encountered_states<br>
At last change the file path in "Final_ProjectDemo" to your Anoconda/Jupyter file path to visualize the automata generated.<br>
• Run the programs in jupyter-lab
