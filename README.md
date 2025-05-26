# Final-Project-Task-3

# Task 3

#include <iostream>
#include <vector>
#include <string>

std::string passwordWithGreatestProduct(const std::vector<std::string>& passwords) {
    std::string result = "";
    long long max_product = 0;
    
    for (const auto& password : passwords) {
        long long product = 1;
        
        //calculate product of ASCII values - O(M) where M is password length
        for (char c : password) {
            product *= static_cast<int>(c);
        }
        
        //password has greater product change
        if (product > max_product) {
            max_product = product;
            result = password;
        }
    }
    
    return result;
}

int main() {
    std::vector<std::string> passwords = {"password123", "hello", "abc", "xyz", "test"};
    
    std::string best_password = passwordWithGreatestProduct(passwords);
    
    std::cout << "Password with greatest product: " << best_password << std::endl;
    
    return 0;
}
