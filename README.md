# Youtube Clone


# Static Website Deployment Flow  

This project demonstrates how static assets (**HTML, CSS, JS, Images, and Videos**) are served to clients via a **Static Host** (e.g., Nginx, GitHub Pages) and optimized using a **CDN (Cache Layer)** for performance.  

## 📌 Architecture Diagram  

![diagram](diagram(4).png)  

## 📖 How It Works  

1. **Client Request**  
   - Browser requests the entry point:  
     ```http
     GET /index.html
     ```

2. **CDN (Cache Layer)**  
   - If cached → returns `200 OK + index.html`.  
   - If not cached → forwards the request to the static host.

3. **Static Host (Nginx / GitHub Pages)**  
   - Stores and serves static files:  
     - HTML Pages  
     - CSS (e.g., `bootstrap.css`)  
     - JS (e.g., `bootstrap.bundle.js`)  
     - Images (`img/`, `img1/`)  
     - Videos (`.mp4`)  

4. **Browser Parses HTML**  
   - After receiving `index.html`, the browser parses it and sends additional requests for assets inside the HTML.

5. **Asset Fetching**  
   - CSS → `GET css/bootstrap.css`  
   - JS → `GET js/bootstrap.bundle.js`  
   - Images → `GET img/*`, `GET img1/*`  
   - Videos → `GET video/*.mp4`  

6. **Response Flow**  
   - CSS → `200 OK + bootstrap.css`  
   - JS → `200 OK + bootstrap.bundle.js`  
   - Images → `200 OK + img files`  
   - Videos → `200 OK + mp4 files`  

## 📂 File Types Served  

- **HTML Pages** → `index.html`  
- **CSS** → `bootstrap.css`  
- **JavaScript** → `bootstrap.bundle.js`  
- **Images** → `img/, img1/`  
- **Videos** → `Radhe Govinda.mp4`, `Rait Zara Si.mp4`, `Pal.mp4`  



## ✅ Benefits  

- Faster loading with **CDN caching**  
- Efficient asset delivery  
- Scalable and reliable static hosting  
- Reduced server load due to cache hits  

---

👉 This README explains the **flow of static assets** from **host → CDN → browser** for optimized website performance.  

