# Pagination Project

## Overview

This project involves creating a pagination system for a dataset of popular baby names. The system includes helper functions and methods to paginate the dataset, provide hypermedia pagination, and handle deletion-resilient pagination.

## Tasks

### Task 0: Simple Helper Function

**Objective**: Write a function named `index_range` that takes two integer arguments, `page` and `page_size`, and returns a tuple of two integers representing the start and end index for a list of pagination parameters.

- **Function Signature**:
  ```python
  def index_range(page: int, page_size: int) -> Tuple[int, int]:
  ```

- **Example**:
  ```python
  res = index_range(1, 7)
  print(res)  # Output: (0, 7)

  res = index_range(page=3, page_size=15)
  print(res)  # Output: (30, 45)
  ```

### Task 1: Simple Pagination

**Objective**: Implement a method named `get_page` in the `Server` class that takes two integer arguments, `page` with a default value of 1 and `page_size` with a default value of 10. The method should return a list of rows representing the requested page of the dataset.

- **Class and Method**:
  ```python
  import csv
  from typing import List

  class Server:
      DATA_FILE = "Popular_Baby_Names.csv"

      def __init__(self):
          self.__dataset = None

      def dataset(self) -> List[List]:
          if self.__dataset is None:
              with open(self.DATA_FILE) as f:
                  reader = csv.reader(f)
                  dataset = [row for row in reader]
              self.__dataset = dataset[1:]
          return self.__dataset

      def get_page(self, page: int = 1, page_size: int = 10) -> List[List]:
          pass
  ```

- **Example**:
  ```python
  server = Server()
  print(server.get_page(1, 3))  # Output: [['2016', 'FEMALE', 'ASIAN AND PACIFIC ISLANDER', 'Olivia', '172', '1'], ...]
  ```

### Task 2: Hypermedia Pagination

**Objective**: Implement a method named `get_hyper` in the `Server` class that takes the same arguments as `get_page` and returns a dictionary with hypermedia pagination details.

- **Method Signature**:
  ```python
  def get_hyper(self, page: int = 1, page_size: int = 10) -> Dict[str, Any]:
  ```

- **Output**:
  - `page_size`: The length of the returned dataset page.
  - `page`: The current page number.
  - `data`: The dataset page (equivalent to the return from `get_page`).
  - `next_page`: Number of the next page, `None` if no next page.
  - `prev_page`: Number of the previous page, `None` if no previous page.
  - `total_pages`: The total number of pages in the dataset as an integer.

- **Example**:
  ```python
  server = Server()
  print(server.get_hyper(1, 2))  # Output: {'page_size': 2, 'page': 1, ...}
  ```

### Task 3: Deletion-resilient Hypermedia Pagination

**Objective**: Implement a method named `get_hyper_index` in the `Server` class that takes two integer arguments, `index` with a default value of `None` and `page_size` with a default value of 10. The method should return a dictionary with deletion-resilient pagination details.

- **Method Signature**:
  ```python
  def get_hyper_index(self, index: int = None, page_size: int = 10) -> Dict[str, Any]:
  ```

- **Output**:
  - `index`: The current start index of the return page.
  - `next_index`: The next index to query with.
  - `page_size`: The current page size.
  - `data`: The actual page of the dataset.

- **Example**:
  ```python
  server = Server()
  server.indexed_dataset()
  print(server.get_hyper_index(3, 2))  # Output: {'index': 3, 'data': [...], 'page_size': 2, 'next_index': 5}
  ```

## Repository Structure

- **GitHub repository**: `alx-backend`
- **Directory**: `0x00-pagination`
- **Files**:
  - `0-simple_helper_function.py`: Contains the `index_range` function.
  - `1-simple_pagination.py`: Contains the `Server` class with the `get_page` method.
  - `2-hypermedia_pagination.py`: Contains the `Server` class with the `get_hyper` method.
  - `3-hypermedia_del_pagination.py`: Contains the `Server` class with the `get_hyper_index` method.

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/alx-backend/alx-backend.git
   ```

2. Navigate to the project directory:
   ```bash
   cd alx-backend/0x00-pagination
   ```

3. Run the main files to test the implementation:
   ```bash
   ./0-main.py
   ./1-main.py
   ./2-main.py
   ./3-main.py
   ```

## License

This project is licensed under the MIT License.

---
