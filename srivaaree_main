import tkinter as tk
from tkinter import filedialog
from PIL import Image, ImageDraw
import os

def add_name_date(img_path, name="MURUGAN D", date="27-04-2025"):
    img = Image.open(img_path).convert("RGB")
    # resize to passport size approx (413×531 px)
    img = img.resize((413, 531))
    draw = ImageDraw.Draw(img)
    draw.text((10, 500), f"{name}\n{date}", fill="black")
    output = os.path.join(os.getcwd(), "photo_output.jpg")
    img.save(output)
    return output

def open_image():
    path = filedialog.askopenfilename(
        filetypes=[("Image Files", "*.jpg *.jpeg *.png")]
    )
    if path:
        out = add_name_date(path)
        status_label.config(text=f"Saved: {out}")

app = tk.Tk()
app.title("Srivaaree Card Master – Photo Tool")

tk.Button(app, text="Upload & Generate", command=open_image).pack(pady=20)
status_label = tk.Label(app, text="")
status_label.pack()

app.geometry("400x200")
app.mainloop()
