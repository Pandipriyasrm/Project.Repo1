const container = document.querySelector('.container');
const seats = document.querySelectorAll('.row .seat:not(.occupied)');
const count = document.getElementById('count');
const total = document.getElementById('total');
const movieSelect = document.getElementById('movie');
const confirmBtn = document.getElementById('confirm');
const confirmation = document.getElementById('confirmation');

let ticketPrice = +movieSelect.value;

// Update total and count
function updateSelectedCount() {
  const selectedSeats = document.querySelectorAll('.row .seat.selected');
  const selectedSeatsCount = selectedSeats.length;

  count.innerText = selectedSeatsCount;
  total.innerText = selectedSeatsCount * ticketPrice;
}

// Seat click event
container.addEventListener('click', (e) => {
  if (e.target.classList.contains('seat') &&
      !e.target.classList.contains('occupied')) {
    e.target.classList.toggle('selected');
    updateSelectedCount();
  }
});

// Movie select event
movieSelect.addEventListener('change', (e) => {
  ticketPrice = +e.target.value;
  updateSelectedCount();
});

// Confirm booking
confirmBtn.addEventListener('click', () => {
  const selectedSeats = document.querySelectorAll('.row .seat.selected');
  if (selectedSeats.length === 0) {
    confirmation.innerText = "Please select at least one seat!";
    confirmation.style.color = "red";
  } else {
    confirmation.innerText = `Booking confirmed for ${selectedSeats.length} seat(s). Total: ₹${selectedSeats.length * ticketPrice}`;
    confirmation.style.color = "green";
  }
});
