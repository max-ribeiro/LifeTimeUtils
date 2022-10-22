# Click & drag em tabelas com scroll
``` js
function handleScrollableTableDrag() {
  let clicked = false;
  let clickX = 0;
  const table = $('.table-scrollable');
  if (table) {
    table.on({
      mousemove: e => {
        clicked && updateScrollPosition(e);
      },
      mousedown: e => {
        clicked = true;
        clickX = e.pageX;
      },
      mouseup: () => {
        clicked = false;
        table.css('cursor', 'auto');
        table.css('user-select', 'auto');
      }
    });

    const updateScrollPosition = e => {
      table.css('cursor', 'grabbing');
      table.css('user-select', 'none');
      table.scrollLeft(table.scrollLeft() + (clickX - e.pageX));
    };
  }
}
//verify right drag
let rightDragging = false;
    $('.modal-content').on(
    {
        mousedown: e => {
            if (e.which == 3) {
                e.preventDefault();
                rightDragging = true;
            }
        },
        mouseup: e => {
            if (e.which == 3) {
                e.preventDefault();
                rightDragging = false;
            }
        },
        mousemove: e => {
            if (rightDragging) {
                e.preventDefault();
            }
        },
        contextmenu: e => {
            e.preventDefault();
        }
    },
    '#map'
);