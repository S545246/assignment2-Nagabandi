# assignment2-Nagabandi
# Nikhil Nagabandi
###### Taj Mahal
I like **Taj Mahal** very much it is one of the most beautiful place in the world and also it is one **tourist place** around the world.

### Travel directions

---

1. First we should book a Fight ticket from the travel booking website from Kansas to Chicago and Chicago to Delhi.
    1. Book a cab OR RENT a car and take a ride from Maryville to Kansas city airport(MCI)
        1. Once reached to Kansas city airport(MCI) take the boarding pass from the counter.
        2. Then travel to chicago from kansas in flight.
2. After boarding the flight in chicago then go ahead and change the terminal from domestic to international.
    1. once arrived in chicago international airport(ORD) take the boarding pass from the counter.
    2. Then travel to Delhi from chicago in flight.
* After boarding the flight in Delhi international airport then go ahead and take the book a cab or Rent a car from Delhi airport to Taj mahal.
    * If we book a cab then Cab driver will take you to Taj mahal directly based on the maps directions.
    * If we rent a cab then go ahead and take a ride till Taj mahal it take 3hrs 30mins to reach the destination
    * The easiest & cheapest way to go to Taj Mahal is via Agra One Volvo Bus one day trip
    * To board the bus simply take a Taxi from the Airport to pick up point at INA Metro Station Gate No.
* Here you go once reached there you can an awesome view of Taj Mahal.
    * Once you reach there you can find and amazing food.
        * Biryani
        * Masala Dosa

**[README Display AboutMe](AboutMe.md)**

## Famous Foods In bangalore

---

The following table consists some of most famous foods that are available in Bangalore.

| Food Item | Loaction | Price |
| --- | --- | --- |
| Chicken Biryani | Krutinga | $8 |
| Masala Dosa | Vidyarthi Bhavan | $5 |
| Mand house | Arabian Mandi | $15 |
| Hard Rock Cafe | Coffie | $6 |

## Pitty Quotes

---

> If life were predictable it would cease to be life, and be without flavor. ***Eleanor Roosevelt***

> Life is what happens when you're busy making other plans. ***John Lennon***

## Code Fencing

---

> Graham's scan is a method of finding the convex hull of a finite set of points in the plane with time complexity O(n log n).

> It is named after Ronald Graham, who published the original algorithm in 1972. The algorithm finds all vertices of the convex hull ordered along its boundary.

<https://en.wikipedia.org/wiki/Graham_scan>

```
struct pt {
    double x, y;
};

bool cmp(pt a, pt b) {
    return a.x < b.x || (a.x == b.x && a.y < b.y);
}

bool cw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) < 0;
}

bool ccw(pt a, pt b, pt c) {
    return a.x*(b.y-c.y)+b.x*(c.y-a.y)+c.x*(a.y-b.y) > 0;
}

void convex_hull(vector<pt>& a) {
    if (a.size() == 1)
        return;

    sort(a.begin(), a.end(), &cmp);
    pt p1 = a[0], p2 = a.back();
    vector<pt> up, down;
    up.push_back(p1);
    down.push_back(p1);
    for (int i = 1; i < (int)a.size(); i++) {
        if (i == a.size() - 1 || cw(p1, a[i], p2)) {
            while (up.size() >= 2 && !cw(up[up.size()-2], up[up.size()-1], a[i]))
                up.pop_back();
            up.push_back(a[i]);
        }
        if (i == a.size() - 1 || ccw(p1, a[i], p2)) {
            while(down.size() >= 2 && !ccw(down[down.size()-2], down[down.size()-1], a[i]))
                down.pop_back();
            down.push_back(a[i]);
        }
    }

    a.clear();
    for (int i = 0; i < (int)up.size(); i++)
        a.push_back(up[i]);
    for (int i = down.size() - 2; i > 0; i--)
        a.push_back(down[i]);
}
```
<https://cp-algorithms.com/geometry/grahams-scan-convex-hull.html>