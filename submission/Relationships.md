# Relationships

| Pair | Choice | Justification |
|------|--------:|---------------|
| `Cinema - Screen` |Composition|`Cinema` owns `Screen` without the cinema, screens cannot exist independently|
| `Screen - Seat` |Composition|`Seat` and `Screen` cannot exist independently because Screen owns Seat if a Screen is removed Seat is also rmoved|
| `Show - Movie` | Association | A `Show` borrows a `Movie`. Cancel the 6 PM show and the movie "3 idiots" still exists and still plays at 9 PM. The show stores a pointer/reference and never deletes it. |
| `Show - Screen` |Association|A `Screen` can still host different `Show` even if one is cancelled. A screen exists independent of a show|
| `Show - ShowSeat` |Composition|`ShowSeat` belongs to a `Show`, if a show is cancelled the seats owned by it are also cancelled. The seats cannot exist independently because they are particular to that specific show.|
| `Booking - Customer` |Association|Neither one owns other. A `Customer` can make many bookings and a `Booking` refers to a Customer|
| `Booking - ShowSeat` |Association|`Booking` will only reserve a `Seat` but not own it. If a customer cancells a booking the ShowSeat will still exist just in a different state.|
| `Booking - Payment` |Dependency|`Booking` doesn't store or own a `Payment`, everything is handelled through BookingService|
| `Payment - UpiPayment` |Inheritance|Because `UpiPayment` is a type of `Payment` it inherits and overrides the pay() method|
| `BookingService - Booking` |Dependency|`BookingService` uses `Booking` objects temporarily during booking process but doesn't maintain persistent references|