test case
<code>
test('Click the list icon to select', async ({ page }) => {
  await enterPlaygroundRoom(page);
  await initEmptyState(page);
  await initThreeList(page);
  await assertRichTexts(page, ['123', '456', '789']);
  await page.mouse.click(100, 165);
  await copyByKeyboard(page);
  await pasteByKeyboard(page);
  await page.mouse.click(100, 230);
  await copyByKeyboard(page);
  await pasteByKeyboard(page);
  await page.mouse.click(100, 290);
  await page.keyboard.press('Backspace', { delay: 50 });
  await page.mouse.click(100, 200);
  await page.keyboard.press('Backspace', { delay: 50 });
});
</code>
<code>
export async function initThreeList(page: Page) {
  await focusRichText(page);
  await page.keyboard.type('-');
  await page.keyboard.press('Space', { delay: 50 });
  await page.keyboard.type('123');
  await pressEnter(page);
  await page.keyboard.type('456');
  await pressEnter(page);
  await page.keyboard.press('Tab', { delay: 50 });
  await page.keyboard.type('789');
}
</code>