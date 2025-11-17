# valid-palindrome
class Solution(object):
    def isPalindrome(self, s):
        """
        :type s: str
        :rtype: bool
        """

        left, right = 0, len(s) - 1

        while left < right:
            # Move left pointer to next alphanumeric
            while left < right and not s[left].isalnum():
                left += 1

            # Move right pointer to previous alphanumeric
            while left < right and not s[right].isalnum():
                right -= 1

            # Compare lowercase characters
            if s[left].lower() != s[right].lower():
                return False

            left += 1
            right -= 1

        return True
