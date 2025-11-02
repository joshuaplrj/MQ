🎼 Quantum Note Detector & Deutsch Algorithm Simulator
This is an interactive web application that bridges real-time audio analysis with quantum computing simulation. It uses your microphone to capture musical notes and then uses that data as the input for a live, step-by-step simulation of Deutsch's Algorithm.
Core Features
 * Real-time Audio Analysis (Web Audio API)
   * Note & Octave Detection: Captures audio from your microphone and performs a live analysis to identify the specific musical note (e.g., A, C\#) and its octave (e.g., 4, 5).
   * Live Waveform: Renders a real-time oscilloscope display (waveform) of the incoming audio on a <canvas> element.
   * Timed Recording: Allows you to set a specific recording duration t (in seconds) for capturing each note.
 * Dynamic Recording Interface
   * Chord Selection Menu: The program starts with a menu to select the number of notes (3, 5, 7, 9, 11, or 13).
   * Guided Recording: For the 3-note chord, the UI dynamically creates three separate "recording stations." It guides you to record each note one by one, with options to "Record" and "Retry" each step.
 * Quantum Algorithm Simulation
   * Audio-to-Problem Mapping: This is the core connection. The program defines a 2-bit black-box function, f(x): \{0,1\} \to \{0,1\}, based on your recordings:
     * f(0) is set to 0 if your first note's octave is even and 1 if it's odd.
     * f(1) is set to 0 if your second note's octave is even and 1 if it's odd.
   * Live Calculation: It runs a classical simulation of the 2-qubit Deutsch Algorithm, showing the mathematical state vector (e.g., |\psi_0\rangle, |\psi_1\rangle, \ldots) at each step.
   * Clear Result: The program first determines classically if your function is Constant (f(0) == f(1)) or Balanced (f(0) \neq f(1)). It then shows that the quantum simulation correctly predicts this property (measuring 0 for Constant, 1 for Balanced) using only a single "query" of the simulated oracle U_f.
Purpose
This application serves as an interactive educational tool to make abstract quantum computing concepts more tangible. By allowing you to use your own voice or instrument to create the problem, it provides a unique, hands-on demonstration of superposition, interference, and quantum advantage in the context of a foundational algorithm.
