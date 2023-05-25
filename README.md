# gggg
#include <iostream>

enum class Season {
    Spring,
    Summer,
    Autumn,
    Winter
};

class Calendar {
public:
    virtual void SeasonsChange() {
        for (int i = 0; i < 4; i++) {
            std::ostream << static_cast<Season>(i); << std::endl;
        }
    }
};

class ReverseCalendar : public Calendar {
public:
    void SeasonsChange() override {
        for (int i = 3; i >= 0; i--) {
            std::ostream << static_cast<Season>(i); << std::endl;
        }
    }
};

int main() {
    Calendar* calendar = new ReverseCalendar();
    calendar->SeasonsChange();
    return 0;
}