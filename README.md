
# LeetCode-Inspired Benchmarking Framework

This framework allows you to benchmark generative models like LLMs against a set of coding problems inspired by LeetCode. The framework is extendable and outputs results in a structured JSON format.

## Files

- `automate_llm_benchmarking.py`: Python script to automate the benchmarking process.
- `leetcode_inspired_100_gpt_benchmark.py`: Python file containing metadata for LeetCode-inspired problems (or any other benchmarks you wish to use).
- `benchmark_results.json`: JSON file containing the results of the benchmark.

## How to Use

### Running the Benchmark

1. Make sure you have Python installed.
2. Place your model's API call or function within the `generate_solution` method in the `ExampleLLMGenerator` class within `automate_llm_benchmarking.py`.
3. Run `automate_llm_benchmarking.py`:

    ```bash
    python automate_llm_benchmarking.py
    ```

    This will generate a `benchmark_results.json` file containing the benchmarking results.

### Understanding the JSON File

The `benchmark_results.json` contains an array of dictionaries, each representing the results for a specific coding problem. Each dictionary contains:

- `Problem`: The description of the problem.
- `Generator`: The name of the generator used to create the solution.
- `Measure`: The name of the measure used to evaluate the solution.
- `Score`: The quantitative score of the solution based on the measure.

### Extending the Framework

#### Adding a new Coding Solution Generator

1. Create a new class that inherits from `CodingSolutionGenerator` in `automate_llm_benchmarking.py`.
2. Implement the `generate_solution` method.

#### Adding a new Measure of Coding

1. Create a new class that inherits from `MeasureOfCoding` in `automate_llm_benchmarking.py`.
2. Implement the `evaluate` method.

After implementing these, add instances of your new classes to the `solution_generators` and `measures` lists when initializing `LeetCodeBenchmarkingFramework`.

For more details, refer to the code in `automate_llm_benchmarking.py`.

## Support and Feedback

For any inquiries, issues, or feedback, please open an issue in the repository.
