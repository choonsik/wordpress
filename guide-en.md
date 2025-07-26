# **User Manual**

## **1\. Introduction**

The 'WordPress XML Converter' is a web application designed to convert XML data exported from a WordPress blog into Markdown and HTML formats, suitable for use with static site generators like Jekyll. It automates the complex migration process, helping you move your content easily and safely.

## **2\. How to Use**

1. **Upload XML File**: Download the .xml file from your WordPress admin dashboard (Tools \> Export) and either drag-and-drop it into the designated area or click to select the file.  
2. **Browse Content**:  
   * **Switch between Posts/Pages**: In the 'Content' tab, click the 'Posts' or 'Pages' sub-tabs to view the list for each content type.  
   * **Search and Filter**: You can quickly find specific content by searching for titles or by combining filters for Year, Category, and Tag.  
3. **Review Conversion Results**:  
   * Select an item from the list to see the detailed view on the right.  
   * **HTML Comparison**: Visually review the conversion by comparing the 'Before' (original links) and 'After' (local paths) HTML side-by-side.  
   * **HTML Source**: View and copy the final, cleaned HTML code (WordPress comments removed, featured image included).  
   * **Markdown Source**: View the Jekyll-ready Markdown code, complete with YAML Front Matter.  
4. **Download Files**:  
   * **Individual Download**: In the detail view, click the .html or .md button in the top-right to download just the current post.  
   * **Download All**: Click the Download All (ZIP) button next to the "Conversion Results" title to download all converted files at once.

## **3\. 'Download All' ZIP File Contents**

The downloaded ZIP file (wordpress-export.zip) is structured as follows:

* \_posts/: Jekyll-ready Markdown posts.  
* pages/: Jekyll-ready Markdown pages.  
* html\_posts/: Converted HTML posts.  
* html\_pages/: Converted HTML pages.  
* media\_urls.txt: A list of all original media file URLs.  
* download\_media.sh: A **script to automatically download all media files** (for macOS/Linux).  
* README.txt: A file with instructions.

### How to Automatically Download Media Files

1. Unzip the downloaded ZIP file.  
2. Open your terminal (e.g., Terminal on macOS, WSL or Git Bash on Windows) and navigate to the unzipped folder.  
3. Make the script executable by running: chmod \+x download\_media.sh  
4. Run the script: ./download\_media.sh

The script will create an assets/media folder and download all media files into it, preserving the original YYYY/MM subfolder structure.

## **4\. Key Feature Details**

* **Featured Image Processing**: Automatically detects the featured image for each post/page, adds it to the Markdown Front Matter as an image: property, and includes it at the top of all HTML outputs.  
* **Media Path Management**: Converts all media links in the content and featured images to relative paths based on /assets/media/, while maintaining WordPress's year/month folder structure.  
* **Code Cleaning**: Removes unnecessary WordPress block comments (e.g., \<\!-- wp:paragraph \--\>) from the final HTML and Markdown for cleaner output.  
* **Accessibility Improvement**: Automatically adds "본문 이미지" (Body Image) as the default text for any alt attributes that are empty in the original content.  
* **Full Theming Support**: Allows users to switch the entire application interface between Light, Dark, and Sepia themes for a comfortable viewing experience.
