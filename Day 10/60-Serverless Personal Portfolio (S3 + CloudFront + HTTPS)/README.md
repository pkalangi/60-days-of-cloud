# Day 10/60 — Serverless Personal Portfolio (S3 + CloudFront + HTTPS)

**Status: LIVE & GLOBAL**  
**Live URL:** https://duz8zhf955cab.cloudfront.net/

### Architecture
Serverless Portfolio

                              ┌─────────────────────┐
                              │     Internet        │
                              └────────▲────────────┘
                                       │ HTTPS
                                       ▼
                         ┌─────────────────────────────┐
                         │       CloudFront CDN        │
                         │   (300+ edge locations)     │
                         └────────────▲────────────────┘
                                      │
                                      ▼
                         ┌─────────────────────────────┐
                         │   S3 Bucket (Static Site)   │
                         │   index.html + assets       │
                         └─────────────────────────────┘


### What I Built
- S3 static website hosting<img width="1920" height="1200" alt="STATIC WEBSITE" src="https://github.com/user-attachments/assets/b444e34d-781e-4068-881b-354477592edb" />

- CloudFront distribution (global CDN)<img width="1920" height="1200" alt="CLOUDFRONT DEPLOYED" src="https://github.com/user-attachments/assets/ce7aaf22-60ce-4dc1-9ade-5736ff62a1d6" />

- Automatic HTTP → HTTPS redirect<img width="1920" height="1200" alt="CLOUDFRONT SETTING" src="https://github.com/user-attachments/assets/f19c94c5-6791-4ba6-9bed-658c964f23e8" />

- Default CloudFront SSL certificate<img width="1920" height="1200" alt="POLICY" src="https://github.com/user-attachments/assets/39c3d2f3-4b9b-4b40-8517-f6384bbf3c02" />

- Zero servers, zero maintenance, free tier forever<img width="1920" height="1200" alt="LIVE PAGE" src="https://github.com/user-attachments/assets/ce742022-55f6-4c83-b8f3-0da0e0dbebbc" />



