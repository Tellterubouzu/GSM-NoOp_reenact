# GSM-NoOp_reenact

GSM-NoOp_reenact is a dataset based on the [GSM-Symbolic paper](https://arxiv.org/html/2410.05229v1), where distracting sentences have been inserted into the GSM8K dataset without affecting the correctness of the answers.

## Features
- **Extension of the GSM8K dataset**: Adds extra information that does not alter the problem's core but misleads the respondent.
- **Ideal for evaluating machine learning models**: Allows testing mathematical reasoning capabilities in the presence of noise.
- **MIT License**: Free to use, modify, and redistribute.

## Data Structure
The dataset follows the structure below:

```json
{
    "base": "Janet’s ducks lay 16 eggs per day. She eats three for breakfast every morning and bakes muffins for her friends every day with four. She sells the remainder at the farmers' market daily for $2 per fresh duck egg. How much in dollars does she make every day at the farmers' market?",
    "noop": "Janet’s ducks lay 16 eggs per day. She eats three for breakfast every morning and bakes muffins for her friends every day with four. She sells the remainder at the farmers' market daily for $2 per fresh duck egg, even though one of the eggs sometimes has a slightly larger shell. How much in dollars does she make every day at the farmers' market?",
    "diff": ", even though one of the eggs sometimes has a slightly larger shell.",
    "answer": "Janet sells 16 - 3 - 4 = <<16-3-4=9>>9 duck eggs a day.\nShe makes 9 * 2 = $<<9*2=18>>18 every day at the farmer’s market.\n#### 18"
}
```

- `base`: The original problem statement from the GSM8K dataset.
- `noop`: The `base` problem with additional misleading but non-impactful text inserted.
- `diff`: The inserted noise text that differentiates `noop` from `base`.
- `answer`: The correct answer corresponding to the `noop` version of the problem.

## Installation & Usage
```bash
# Clone the repository
git clone https://github.com/Tellterubouzu/GSM-NoOp_reenact.git
cd GSM-NoOp_reenact

# Check the dataset
cat data/gsm_noop.json
```

## License
This project is licensed under the [MIT License](LICENSE).

## Author
[Tellterubouzu](https://github.com/Tellterubouzu)

