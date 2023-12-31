เพื่อย้อนกลับไป Commit เดิม สามารถใช้คำสั่ง `git revert` ได้ คำสั่ง `git revert` จะใช้สร้าง Commit ใหม่ขึ้นมา เพื่อทำการเปลี่ยนแปลงที่ตรงกันข้ามกับ Commit เดิม

ตัวอย่างเช่น หากต้องการย้อนกลับไป Commit เดิมที่ชื่อ `commit_id` ให้ใช้คำสั่งดังนี้

```
git revert commit_id
```

คำสั่งนี้จะทำการสร้าง Commit ใหม่ขึ้นมา เพื่อทำการเปลี่ยนแปลงที่ตรงกันข้ามกับ Commit เดิมที่ชื่อ `commit_id`

หากต้องการย้อนกลับไป Commit เดิมล่าสุด ให้ใช้คำสั่งดังนี้

```
git revert HEAD
```

คำสั่งนี้จะทำการสร้าง Commit ใหม่ขึ้นมา เพื่อทำการเปลี่ยนแปลงที่ตรงกันข้ามกับ Commit เดิมล่าสุด

หากต้องการย้อนกลับไป Commit เดิมที่เป็นการ Merge ให้ใช้คำสั่งดังนี้

```
git revert -m 1 commit_id
```

คำสั่งนี้จะทำการสร้าง Commit ใหม่ขึ้นมา เพื่อทำการเปลี่ยนแปลงที่ตรงกันข้ามกับ Commit เดิมที่เป็นการ Merge ที่ชื่อ `commit_id`

สิ่งสำคัญที่ต้องทราบคือ คำสั่ง `git revert` จะทำการสร้าง Commit ใหม่ขึ้นมา เพื่อทำการเปลี่ยนแปลงที่ตรงกันข้ามกับ Commit เดิม การเปลี่ยนแปลงที่เกิดขึ้นใน Commit เดิมจะถูกยกเลิกใน Commit ใหม่ ดังนั้น หากต้องการย้อนกลับไป Commit เดิม และต้องการแก้ไขการเปลี่ยนแปลงใน Commit เดิมด้วย ให้ใช้คำสั่ง `git revert --amend` แทน

คำสั่ง `git revert --amend` จะใช้แก้ไข Commit ล่าสุด โดยทำการเปลี่ยนแปลงที่ตรงกันข้ามกับ Commit เดิม การเปลี่ยนแปลงที่เกิดขึ้นใน Commit เดิมจะถูกยกเลิกใน Commit ล่าสุด