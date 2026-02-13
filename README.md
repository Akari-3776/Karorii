document.getElementById("calcBtn").addEventListener("click", () => {
  const calPerItem = Number(document.getElementById("calPerItem").value);
  const quantity = Number(document.getElementById("quantity").value);
  const targetCal = Number(document.getElementById("targetCal").value);

  if (!calPerItem || !quantity || !targetCal) {
    document.getElementById("result").textContent = "すべての数値を入力してください。";
    return;
  }

  const total = calPerItem * quantity;
  const diff = targetCal - total;

  let message = `合計カロリー：${total} kcal\n`;

  if (diff > 0) {
    message += `目標まであと ${diff} kcal`;
  } else if (diff === 0) {
    message += `目標ちょうどです！`;
  } else {
    message += `目標を ${Math.abs(diff)} kcal 超えています`;
  }

  document.getElementById("result").textContent = message;
});
