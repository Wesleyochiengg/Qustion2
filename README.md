#include <iostream>
#include <string>

class Movie {
private:
    std::string title;
    std::string director;
    int duration; // in minutes
    float rating;

public:
    Movie(std::string t, std::string d, int dur, float r) 
        : title(t), director(d), duration(dur), rating(r) {}

    void display() {
        std::cout << "Title: " << title << std::endl;
        std::cout << "Director: " << director << std::endl;
        std::cout << "Duration: " << duration << " minutes" << std::endl;
        std::cout << "Rating: " << rating << std::endl;
    }

    void rateMovie(float newRating) {
        if (newRating >= 1.0 && newRating <= 5.0) {
            rating = newRating;
        } else {
            std::cout << "Invalid rating" << std::endl;
        }
    }
};

int main() {
    Movie movie("Inception", "Christopher Nolan", 148, 4.8);
    movie.display();

    movie.rateMovie(5.0);
    movie.display();

    movie.rateMovie(6.0);

    return 0;
}
