# 🤖 GitHub Badge Bot

> **The ultimate GitHub achievement hunter.** Set it up once, collect ALL badges automatically.

![Badges Hunted](https://img.shields.io/badge/badges%20hunted-9-brightgreen)
![Runs every hour](https://img.shields.io/badge/schedule-hourly-blue)
![Telegram](https://img.shields.io/badge/notifications-Telegram-26A5E4)
![Free tier](https://img.shields.io/badge/cost-free-success)

---

## 🎯 ALL Badges This Bot Hunts

### 🤖 Fully Automated (set & forget)

| Badge | How | Tier Progress |
|---|---|---|
| ⚡ **Quickdraw** | Opens + closes issue instantly | One-time ✅ |
| 🤙 **YOLO** | Merges PR without review | One-time ✅ |
| 🦈 **Pull Shark** | Auto-creates + merges PRs hourly | 🥉2 → 🥈16 → 🥇128 PRs |
| ❤️ **Heart On Your Sleeve** | Auto-reacts ❤️ to content daily | Beta badge |

### 🔧 Semi-Automated (one-click trigger)

| Badge | How | Tier Progress |
|---|---|---|
| 🔗 **Pair Extraordinaire** | Enter co-author → auto PR+merge | 🥉1 → 🥈10 → 🥇24 PRs |
| 🧠 **Galaxy Brain** | Creates Discussions + reminds you | 🥉1 → 🥈10 → 🥇25 answers |
| 🌐 **Open Sourcerer** | Finds repos + reminds to contribute | Beta badge |

### 📝 Manual (bot guides you with reminders)

| Badge | How | Cost |
|---|---|---|
| ⭐ **Starstruck** | Bot keeps repo fresh + tracks stars | Free (need 16+ stars) |
| 💖 **Public Sponsor** | Bot sends link → sponsor someone $1/mo | $1/month |
| 🏅 **Developer Program** | Bot sends link → sign up (FREE) | Free |

---

## ⚡ Setup (5 minutes)

### Step 1 — Personal Access Token (GH_PAT)

**CRITICAL:** For the badges to be credited to YOUR profile instead of the bot, you must use a Personal Access Token.
1. Go to [Personal Access Tokens (classic)](https://github.com/settings/tokens).
2. Click **Generate new token (classic)**.
3. Check the **`repo`** scope (this gives the bot permission to create PRs and discussions).
4. Generate the token and copy it.
5. Go to your Badge Hunter repository **Settings** → **Secrets and variables** → **Actions**.
6. Add a new repository secret named `GH_PAT` and paste your token.

### Step 2 — Repo Settings

1. Go to **Settings** → **Actions** → **General**
2. **Workflow permissions** → ✅ **Read and write permissions**
3. ✅ **Allow GitHub Actions to create and approve pull requests**
4. **Save**

### Step 3 — Telegram Bot (for live notifications)

1. Open Telegram → search **@BotFather** → `/newbot`
2. Copy the **bot token**
3. Send any message to your new bot, then visit:
   ```
   https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates
   ```
4. Copy your **chat_id** from the response
5. In your repo → **Settings** → **Secrets and variables** → **Actions**:
   - Add secret: `TELEGRAM_BOT_TOKEN` = your bot token
   - Add secret: `TELEGRAM_CHAT_ID` = your chat ID

### Step 4 — Launch! 🚀

Go to **Actions** tab → **Badge Bot Master** → **Run workflow**

That's it. The bot runs every hour automatically and sends Telegram updates.

---

## 📁 Workflow Files

```
.github/workflows/
├── badge-bot.yml              ← 🤖 Master orchestrator (hourly)
├── pull-shark.yml             ← 🦈 Pull Shark + YOLO (hourly)
├── quickdraw.yml              ← ⚡ Quickdraw (auto, once)
├── pair-extraordinaire.yml    ← 🔗 Pair Extraordinaire (manual)
├── galaxy-brain.yml           ← 🧠 Galaxy Brain helper (daily)
├── starstruck.yml             ← ⭐ Starstruck tracker (daily)
├── open-sourcerer.yml         ← 🌐 Open Sourcerer helper (4-hourly)
├── heart-on-sleeve.yml        ← ❤️ Heart On Your Sleeve (daily)
├── public-sponsor.yml         ← 💖 Public Sponsor reminder (weekly)
└── dev-program.yml            ← 🏅 Developer Program reminder (weekly)
```

---

## 📊 Pull Shark Progress Calculator

| Tier | PRs Needed | Time at 1/hr | Time at 24/day |
|---|---|---|---|
| 🥉 Bronze | 2 | ~2 hours | ~2 hours |
| 🥈 Silver | 16 | ~16 hours | ~1 day |
| 🥇 Gold | 128 | ~5 days | ~5 days |

---

## 📱 Telegram Notifications

The bot sends you live updates including:

- 🟢 **Hunt started** — when each cycle begins
- 🦈 **PR progress** — current count & next tier
- 🎉 **Tier unlocks** — instant notification when you reach a new tier
- 📊 **Full reports** — badge dashboard after each hunt
- 💡 **Reminders** — weekly nudges for manual badges

---

## 🔗 Pair Extraordinaire Setup

1. Go to **Actions** → **Pair Extraordinaire Hunter** → **Run workflow**
2. Enter your co-author's GitHub username
3. Enter email: `username@users.noreply.github.com`
4. Set count (up to 10 per run)
5. Click **Run** — it creates + merges co-authored PRs automatically

---

## 🚀 Quick Start Checklist

- [ ] Enable Actions write permissions + PR creation
- [ ] Add `TELEGRAM_BOT_TOKEN` and `TELEGRAM_CHAT_ID` secrets
- [ ] Run **Badge Bot Master** from Actions tab
- [ ] Run **Pair Extraordinaire** with a co-author
- [ ] Run **Galaxy Brain** to set up Discussion tracking
- [ ] Sign up at [developer.github.com/program](https://developer.github.com/program/) (free)
- [ ] Sponsor someone for $1/month at [github.com/sponsors/explore](https://github.com/sponsors/explore)
- [ ] Share repo for ⭐ stars → [r/coolgithubprojects](https://reddit.com/r/coolgithubprojects)
- [ ] Check badges at: `https://github.com/YOUR_USERNAME`

---

## 💡 Pro Tips

- Badges take **minutes to hours** to appear after the trigger action
- **Pull Shark Gold** (128 PRs) takes ~5 days with hourly runs — be patient
- For **Pair Extraordinaire**, use a friend's noreply email: `username@users.noreply.github.com`
- **Galaxy Brain** requires REAL answers — go answer questions in popular repos
- Run **Pair Extraordinaire** with count=10 to batch create co-authored PRs
- Telegram is optional but recommended — you'll know exactly when badges unlock

---

*Last updated: 2026-05-19 · ⭐ 0 stars · Badge Bot 🤖*





package book.catalog;

import java.time.LocalDate;
import java.time.format.DateTimeFormatter;
import java.util.List;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.ModelAttribute;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestParam;

import book.catalog.Service.BookCatalogService;

@Controller
public class BookController {

    @Autowired
    private BookCatalogService bookService;

    // -------------------------------------------------------------------------
    // GET /  →  home page, shows all books
    // -------------------------------------------------------------------------
    @GetMapping("/")
    public String homePage(Model model) {
        List<Book> books = bookService.getAllBooks();
        model.addAttribute("books", books);
        return "home";
    }

    // -------------------------------------------------------------------------
    // GET /add-book-page  →  form to add a new book
    // -------------------------------------------------------------------------
    @GetMapping("/add-book-page")
    public String addBookPage() {
        return "add-book";
    }

    // -------------------------------------------------------------------------
    // POST /add-new-book  →  persist new book, redirect home
    // -------------------------------------------------------------------------
    @PostMapping("/add-new-book")
    public String addNewBook(
            @RequestParam("title") String title,
            @RequestParam("author") String author,
            @RequestParam("genre") String genre,
            @RequestParam("numberOfPages") int numberOfPages,
            @RequestParam("publishedDate") LocalDate publishedDate) {

        bookService.addBook(title, author, genre, numberOfPages, publishedDate);
        return "redirect:/";
    }

    // -------------------------------------------------------------------------
    // GET /edit-book-page/{id}  →  pre-filled edit form for the given book
    // -------------------------------------------------------------------------
    @GetMapping("/edit-book-page/{id}")
    public String editBookPage(@PathVariable("id") long id, Model model) {
        List<Book> books = bookService.getAllBooks();
        int index = bookService.binarySearch(id);

        // If book not found, fall back to home
        if (index == -1) {
            return "redirect:/";
        }

        Book book = books.get(index);

        // Format date as ISO string (yyyy-MM-dd) for the HTML date input
        String formattedDate = book.getPublishedDate()
                .format(DateTimeFormatter.ISO_LOCAL_DATE);

        model.addAttribute("book", book);
        model.addAttribute("date", formattedDate);
        return "edit-book";
    }

    // -------------------------------------------------------------------------
    // POST /update-book  →  apply edits, redirect home
    // -------------------------------------------------------------------------
    @PostMapping("/update-book")
    public String updateBook(@ModelAttribute Book editedBook) {
        bookService.updateBook(editedBook);
        return "redirect:/";
    }

    // -------------------------------------------------------------------------
    // POST /delete-book/{id}  →  remove book by id, redirect home
    // -------------------------------------------------------------------------
    @PostMapping("/delete-book/{id}")
    public String deleteBook(@PathVariable("id") long id) {
        bookService.removeBook(id);
        return "redirect:/";
    }
}




catalog 

package book.catalog.Service;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.lang.reflect.Type;
import java.time.LocalDate;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
import java.util.stream.Collectors;

import org.springframework.stereotype.Service;

import com.google.gson.Gson;
import com.google.gson.GsonBuilder;
import com.google.gson.JsonSyntaxException;
import com.google.gson.reflect.TypeToken;

import book.catalog.Book;
import book.catalog.LocalDateAdapter;

@Service
public class BookCatalogService {

    private List<Book> books = new ArrayList<>();

    public BookCatalogService() {
        GsonBuilder gsonBuilder = new GsonBuilder();
        gsonBuilder.registerTypeAdapter(LocalDate.class, new LocalDateAdapter());
        Gson gson = gsonBuilder.create();
        Type listType = new TypeToken<List<Book>>() {}.getType();

        // Use classpath loading so it works both at runtime and during tests
        try (InputStream is = getClass().getClassLoader().getResourceAsStream("books.json");
             BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(is))) {

            List<Book> importedBooks = gson.fromJson(bufferedReader, listType);

            if (importedBooks != null) {
                for (Book b : importedBooks) {
                    if (b != null) {
                        this.books.add(b);
                    }
                }
                sortById();
            }

        } catch (IOException | JsonSyntaxException | NullPointerException e) {
            System.err.println("Unable to read books.json: " + e.getMessage());
        }
    }

    public void sortById() {
        Collections.sort(this.books, new Comparator<Book>() {
            @Override
            public int compare(Book book1, Book book2) {
                return Integer.compare(book1.getId(), book2.getId());
            }
        });
    }

    public List<Book> getAllBooks() {
        // Defensive filter — never return nulls to the template
        return this.books.stream()
                .filter(b -> b != null)
                .collect(Collectors.toList());
    }

    public int binarySearch(long id) {
        int start = 0;
        int end = this.books.size() - 1;

        while (start <= end) {
            int mid = (start + end) / 2;
            long midValue = this.books.get(mid).getId();

            if (midValue == id) {
                return mid;
            } else if (midValue > id) {
                end = mid - 1;
            } else {
                start = mid + 1;
            }
        }
        return -1;
    }

    public void addBook(String title, String author, String genre,
                        int numberOfPages, LocalDate publishedDate) {
        // New ID = current size + 1
        int newId = this.books.size() + 1;
        Book newBook = new Book(newId, title, author, genre, numberOfPages, publishedDate);
        this.books.add(newBook);
    }

    public void updateBook(Book updatedBook) {
        // Index = ID - 1 (IDs are 1-based)
        int index = updatedBook.getId() - 1;

        if (index >= 0 && index < this.books.size()) {
            Book existingBook = this.books.get(index);
            existingBook.setTitle(updatedBook.getTitle());
            existingBook.setAuthor(updatedBook.getAuthor());
            existingBook.setGenre(updatedBook.getGenre());
            existingBook.setNumberOfPages(updatedBook.getNumberOfPages());
            existingBook.setPublishedDate(updatedBook.getPublishedDate());
        }
    }

    public void removeBook(long id) {
        int index = binarySearch(id);
        if (index != -1) {
            this.books.remove(index);
        }
    }
}

