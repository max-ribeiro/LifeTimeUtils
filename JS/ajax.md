# Handler para busca em input[type=search] por ajax
> precisa de melhorias
``` js
let timer;
const interval = 5000;
$(document).on('keyup', () => {
  clearTimeout(timer);
  logger.log('digitando...');
  timer = setTimeout(() => {
    logger.log('parou de digitar.');
  }, interval);
});

$(document).on('keydown', function() {
  clearTimeout(timer);
});
```