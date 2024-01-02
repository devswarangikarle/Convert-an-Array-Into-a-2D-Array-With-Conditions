# Convert-an-Array-Into-a-2D-Array-With-Conditions

class Solution:
    def findMatrix(self, nums):
        result = []
        count_map = {}

        # Count the frequency of each number in the input list
        for num in nums:
            count_map[num] = count_map.get(num, 0) + 1

        # Construct the result matrix based on the frequency map
        while count_map:
            temp_row = []

            for key, count in list(count_map.items()):
                temp_row.append(key)
                count_map[key] -= 1

                if count_map[key] == 0:
                    del count_map[key]

            result.append(temp_row)

        return result
