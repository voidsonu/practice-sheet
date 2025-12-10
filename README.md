# practice-sheet
This includes all the numerical and question practice of DSA or JS or MYSQL questions

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX---- DAY DSA with JSXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
Q1. DSA — Find the element that appears only once in an array

You are given an integer array where:

Every element appears twice

Except one element, which appears only once

Example:
Input: [4, 1, 2, 1, 2]
Output: 4

Ans.
function findUnique(arr) {
    let xor = 0;

    // Step 1: XOR to get candidate
    for (let num of arr) {
        xor ^= num;
    }

    // Step 2: Count occurrences of the candidate
    let count = 0;
    for (let num of arr) {
        if (num === xor) count++;
    }

    // Step 3: Validate
    return count === 1 ? xor : null;  // null = no unique value
}

// Tests:
console.log(findUnique([1,1,2,2,3,3])); // null (no unique)
console.log(findUnique([4,1,2,1,2]));   // 4
console.log(findUnique([0,5,5]));       // 0

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX---------------------------- MYSQL NOW 
Q1. Find employees who earn more than the average salary of their department

SELECT 
    e.emp_name,
    e.salary,
    d.department_name
FROM employees e
JOIN department d ON d.dept_id = e.dept_id
WHERE e.salary > (
    SELECT AVG(e2.salary)
    FROM employees e2
    WHERE e2.dept_id = e.dept_id
);



SELECT AVG(e2.salary)
FROM employees e2
WHERE e2.dept_id = e.dept_id
