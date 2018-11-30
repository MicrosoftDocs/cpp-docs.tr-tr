# <a name="metadata-and-markdown-template"></a>Meta veriler ve Markdown şablonu

Bu docs çekirdek şablon meta verileri ayarlama yönergeleri yanı sıra, Markdown söz dizimi örneklerini içerir. Bu en iyi almak için her ikisini de görüntülemek gerekir [ham Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) ve [görünüm işlenen](https://github.com/dotnet/docs/blob/master/styleguide/template.md) (işlenmiş görünümle çalışmazken örneği için ham Markdown meta veriler bloğu gösterir).

Bir Markdown dosyası oluştururken, bu şablon için yeni bir dosya kopyalama, meta verileri, H1 başlığını üst kısımda makalenin başlığı aşağıda belirtilen kümesi doldurun ve içeriği silmeniz gerekir.

## <a name="metadata"></a>Meta Veriler

Tüm meta veriler bloğu üstünde olan (içinde [ham Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), gerekli alanları ve isteğe bağlı alanları ayrılmıştır. Bazı önemli notlar:

- **Gerekir** arasında iki nokta üst üste (:) ve bir meta veri öğesinin değeri bir alana sahip.
- İsteğe bağlı meta veri öğesi bir değer yoksa, # öğeyi açıklama satırı yapın ya da (dahil değil "na" kullanmayın veya boş bırakın); kaldırın Açıklama satırı bir öğeye bir değer ekliyorsanız, # kaldırmak emin olun.
- Bir değer (örneğin, bir başlık) içerisindeki iki nokta işaretleri meta veri ayrıştırıcısını durdurur. Bu durumda, çift tırnak işareti başlığıyla çevreleyen (örneğin, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).
- **Başlık**: Bu başlık, arama motoru sonuçlarında görünür. Ürün adından önce gelen bir çizgi (|) de ekleyebilirsiniz (örneğin, `title: Developing Libraries with Cross Platform Tools | .NET Core`). Başlık, H1 başlığını başlığında aynı olması değil ve 65 karakter içermelidir veya daha az (dahil olmak üzere | ÜRÜN ADI).
- **Yazar**, **manager**, **ms.reviewer**: Yazar alanı içermelidir **GitHub kullanıcı adını** değil diğer yazar.  Öte yandan, "Yönetici" ve "ms.reviewer" alanları, Microsoft adlar içermelidir. MS.Reviewer makale veya özellik ile ilişkili PM geliştirme adını belirtir.
- **MS.devlang** teknoloji tanımlar. Desteklenen değerler şunlardır: `dotnet`, `cpp`, `csharp`, `fsharp`, `vb` ve `xml`.
- **MS.assetid**: Business Intelligence (BI) gibi iç izleme amacıyla kullanılan makalenin GUID budur. Yeni bir Markdown dosyası oluştururken, adresinden bir GUID alın [çevrimiçi GUID Oluşturucu](https://www.guidgenerator.com/).

## <a name="basic-markdown-gfm-and-special-characters"></a>Temel Markdown ve GFM özel karakterler

Tüm temel ve GitHub Flavored Markdown (GFM) desteklenir. Bunlar hakkında daha fazla bilgi için bkz:

- [Temel Markdown söz dizimi](https://daringfireball.net/projects/markdown/syntax)
- [GFM belgeleri](https://guides.github.com/features/mastering-markdown)

Markdown kullanan özel karakterler gibi \*, \`, ve \# biçimlendirme. Bu karakterlerden biri, içeriğinizi eklemek isterseniz, ikisinden birini yapmanız gerekir:

- ", Kaçış için" özel karakter önce ters eğik çizgi yerleştirmek (örneğin, `\*` için bir \*)
- Kullanım [HTML varlık kodu](https://www.ascii.cl/htmlcodes.htm) karakter (örneğin, `&#42;` için bir &#42;).

## <a name="markdown-editing-tools"></a>Markdown düzenleme araçları

Kullanabileceğiniz [Visual Studio Code](https://code.visualstudio.com/) Markdown belgeleri düzenlemek için. VS Code gibi birçok yararlı Markdown uzantıları sahiptir:

- [docs markdown](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown) Microsoft tarafından
- [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)

## <a name="file-name"></a>Dosya adı

Dosya adlarında aşağıdaki kurallar kullanılır:

- Yalnızca küçük harf, sayı ve kısa çizgi içermelidir.
- Boşluk veya noktalama karakteri kullanmayın. Sözcükleri ve sayıları dosya adını ayırmak için kısa çizgi kullanın.
- Gibi belirli eylem fiilleri kullanın geliştir, satın alma, yapı, sorun giderme. -İng sözcükleri yok.
- Küçük kelimeleri yok - eklenmeyen bir ve, içinde veya gibi.
- Markdown içinde olmalı ve .md dosya uzantısını kullanmanız gerekir.
- Dosya adlarını makul ölçüde kısa tutun. Bunlar, makalelerinizin URL'sini parçasıdır.  

## <a name="headings"></a>Başlıkları

Stil cümle büyük/küçük harf kullanın. Her zaman büyük harfe çevirme:

- İlk sözcük başlığın.
- İki nokta üst üste bir başlık ya da başlığı aşağıdaki sözcük (örneğin, "nasıl yapılır: bir diziyi sıralamak").

Başlıkları yapılması atx stili kullanarak, diğer bir deyişle, 1-6 karma karakter (#) satırın başlangıcında ila H6 HTML başlıkları düzeyleri H1 karşılık gelen bir başlığı, belirtmek için kullanın. Birinci ve ikinci düzey üstbilgileri örnekleri yukarıda kullanılır.

Orada **gerekir** sayfadaki başlığı görüntülenecek Konunuza yalnızca bir birinci düzey başlık (H1) olabilir.

Başlığı ile sonuçlansa bir `#` karakter, gereken ek eklemek `#` başlığının doğru bir şekilde işlemek sırada uçtaki karakter. Örneğin: `# Async Programming in F# #`

Her zaman olmalıdır bir boş satır önce ve sonra başlık (hariç, birinci düzey başlıkları).

İkinci düzey başlıklar sayfa üzerindeki başlığın altında "Bu makaledeki" bölümünde görünen sayfa üzerindeki İçindekiler Listesini oluşturur.

```markdown
### Third-level heading

#### Fourth-level heading

##### Fifth level heading

###### Sixth-level heading
```

## <a name="text-styling"></a>Metin stili oluşturma

*İtalik*  
Kullanıcı tarafından oluşturulan dosya adları, klasör ve yolları (kendi satırına bölme uzun öğeleri için); için kullanın Yeni hüküm; parametre adları; kullanıcı tarafından girilen değerler; ve URL'leri (varsayılan değer olan bağlantılar olarak işlenmiş sürece).

**Kalın**  
Kullanıcı Arabirimi öğeleri ve dil anahtar sözcükleri için kullanın.

## <a name="links"></a>Bağlantılar

### <a name="internal-links"></a>İç bağlantı

(Yer işareti bağlantıları olarak da bilinir) aynı Markdown dosyasındaki bir üst bilgiye bağlantı sağlamak için bağlanmaya çalıştığınız üst bilgisi kimliği öğrenmek gerekir. Kimliğini onaylamak için işlenen makalenin kaynağını görüntüleyerek, başlığının kimliğini bulun (örneğin, `id="blockquote"`) ve # + kimlik kullanarak bağlantıyı (örneğin, `#blockquote`).
Kimliği üst bilgisi metne göre otomatik olarak üretilir. Bu nedenle, örneğin, adlı benzersiz bir bölümde verilen `## Step 2`, kodu şuna benzer `id="step-2"`.

- Örnek: [bölüm 1](#chapter-1)

Aynı depodaki bir Markdown dosyasına bağlantı sağlamak kullanın [göreli bağlantıları](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), dosya adının sonuna ".md" dahil.

- Örnek: [Benioku dosyası](../readme.md)
- Örnek: [.NET hoşgeldiniz](../docs/welcome.md)

Aynı depodaki bir Markdown dosyasındaki bir üst bilgiye bağlantı sağlamak göreli bağlantı sağlama ve diyez etiketli bağlantı kullanın.

- Örnek: [.NET topluluk](../docs/welcome.md#community)

### <a name="docs-links"></a>Docs bağlantıları

Farklı bir Docs depodaki dosyaya bağlantı sağlamak için bağlantı olarak docs.microsoft.com göreli URL kullanın. .Md soneki içermez.

- Örnek: [Evrensel Windows platformu belgeleri](/windows/uwp)

### <a name="external-links"></a>Dış bağlantılar

Harici bir dosyaya bağlantı sağlamak için bağlantı olarak tam URL'yi kullanın. Varsa HTTPS URL'sini kullanın.

- Örnek: [GitHub](https://www.github.com)

Bir Markdown dosyasında bir URL görünürse, tıklanabilir bir bağlantıya dönüştürülür.

- Örnek: https://www.github.com

### <a name="links-to-apis"></a>API'lerin bağlantıları

Derleme sistemi sağlayan dış bağlantıları kullanmak zorunda kalmadan için .NET Core API'ları bağlamak bize bazı uzantılar vardır.  
API'ye bağlantı oluştururken API'nin kaynak koddan otomatik olarak oluşturulan kendi benzersiz tanımlayıcısını (UID) kullanabilirsiniz.

Aşağıdaki söz dizimini kullanabilirsiniz:

1. Markdown bağlantısı: `[link_text](xref:UID)`
2. Otomatik bağlantı: `<xref:UID>`
3. Toplu formu: `@UID`

- Örnek: `@System.String`
- Örnek: `[String class](xref:System.String)`

Bu gösterimi kullanma hakkında daha fazla bilgi için bkz. [çapraz başvuruyu kullanma](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).

> Şu anda, Uıd'leri bulmanın kolay bir yolu yoktur. Bu depoda aramak için bir API için UID bulmak için en iyi yolu: [docascode/coreapi](https://github.com/docascode/coreapi). Daha iyi bir sistem ileride çalışıyoruz.

Özel karakterlerini içerdiğinde UID \` veya \#, UID değerinin %60 ve % 23 sırasıyla aşağıdaki örneklerde gösterildiği gibi kodlanmış HTML olması gerekir:
- Örnek: @System.Threading.Tasks.Task \`1 olur. `@System.Threading.Tasks.Task%601`
- Örnek: @System.Exception.\# ctor olur `@System.Exception.%23ctor`

## <a name="lists"></a>Listeler

Listeleri tarafından boş satırlar arasında olmalıdır.

### <a name="ordered-lists"></a>Sıralı listeler

1. Bu
1. olduğu
1. Bir
1. Sıralı
1. List

#### <a name="ordered-list-with-an-embedded-list"></a>Sıralı liste ile bir gömülü liste

1. Burada
1. gelir
1. Bir
1. Katıştırılmış
    1. Deniz Acar
    1. Turgay elmas
1. ordered
1. liste

### <a name="unordered-lists"></a>Sırasız listeler

- Bu
- is
- a
- Madde işaretli
- liste

#### <a name="unordered-list-with-an-embedded-list"></a>Katıştırılmış bir liste bulunan sırasız liste

- Bu
- Madde işaretli
- liste
    - Emel Mert
    - Murat Arslan
- içerir  
- Diğer
    1. Abdullah kurt
    1. Merve Demir
- listeler

## <a name="horizontal-rule"></a>Yatay cetvel

___

## <a name="tables"></a>Tabloları

| Tabloları        | Olan           | seyrek erişimli  |
| ------------- |:-------------:| -----:|
| 3. sütun      | sağa hizalı | $1600 |
| 2. sütun      | Orta      |   $12 |
| varsayılan sütun 1 | Sola Hizala     |    $1 |

Kullanabileceğiniz bir [Markdown tablo Oluşturucu aracı](https://www.tablesgenerator.com/markdown_tables) daha kolay oluşturmaya yardımcı olmak için. Ayrıca bkz: [düzenleme araçları Markdown](#markdown-editing-tools).

## <a name="code"></a>Kod

Kod eklemek için en iyi yolu, bir çalışma örnekten parçacıkları eklemektir. Bölümündeki yönergeleri izleyerek örneğinizi oluşturma [katkıda bulunan Kılavuzu](../CONTRIBUTING.md#contributing-to-samples).

Kodu içerebilir söz dizimi kullanmayı içerir:

```markdown
[!code-csharp[<title>](<pathToFile>#<RegionName)]
```

Yukarıda gösterildiği örnek C# sözdizimi, ancak diğer dil desteklenir.
Kullanma `code-fsharp` için F# örnekleri; kullanım `code-vbnet` Visual Basic örnekleri için.
Desteklenen diğer diller şunlardır:

- C++: `code-cpp`
- HTML: `code-html`
- JavaScript: `code-javascript`
- PowerShell: `code-ps`
- SQL: `code-sql`
- XML: `code-xml`

Yerleştirmek için metin `<title>` geçişe metin olarak gösterilir. `<pathToFile>` Kaynak dosyasının yolu. `<RegionName>` Dahil edilmesi gereken kaynak kodunuzu bölgesinde olmalıdır. Kullanım `#region` ve `#endregion` eklemek için kod belirtmesine önişlemci söz dizimini kullanın.

Burada bölgeleri çalışmaz durumlarda, başlangıç ve bitiş bir XML öğesi adı tek satırlı açıklama kullanarak bir parçacığı belirtebilirsiniz. Örneğin, bu yazabilirsiniz C#:

```csharp
// <CodeToInclude>
int j = 5;
int i ; 10;
int sum = i + j;
// </CodeToInclude>
```

Diğer dillerde, bu dil için açıklama söz dizimi kullanın.

Son olarak, satır numaralarını kullanabilirsiniz: `#L1-L10` 1-10 arasındaki satırları içerir. Çok kırılır çünkü biz satır numaralarını önleyin.

Kod parçacıkları tam programlarından dahil olmak üzere tüm kod sürekli tümleştirme (CI) sistemimiz çalıştırmasını sağlar. Ancak, bir derleme zamanı veya çalışma zamanı hataları neden göstermek gerekiyorsa, satır içi kod blokları kullanabilirsiniz.

### <a name="inline-code-blocks-with-language-identifier"></a>Satır içi kod blokları, dil tanımlayıcısı

Üç tik kullanın (\`\`\`) + kodlama bir kod bloğu için dile özgü renk uygulamak için bir dil kimliği. Tüm işte [GFM dil kimliği](https://github.com/jmm/gfm-lang-ids/wiki/GitHub-Flavored-Markdown-(GFM)-language-IDs).

#### <a name="c"></a>C\#

```csharp
using System;
namespace HelloWorld
{
    class Hello
    {
        static void Main() 
        {
            Console.WriteLine("Hello World!");

            // Keep the console window open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

#### <a name="python"></a>Python

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a>PowerShell

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a>Genel bir kod bloğu

Üç tik kullanın (&#96;&#96;&#96;) genel bir kod bloğu kodlama için.

> Doğru sözdizimi vurgulama belgeleri sitede emin olmak için önceki bölümde açıklandığı gibi Dil tanımlayıcıları ile kod blokları kullanmak için önerilen yaklaşımdır bakın. Genel kod blokları yalnızca gerekli olduğunda kullanın.

```javascript
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

### <a name="inline-code"></a>Satır içi kod

Tik kullanın (&#96;) için `inline code`. Satır içi kod, komut satırı komutlarını, veritabanı tablo ve sütun adları ve dili ifadeleri için işlev adlarını kullanın.

## <a name="blockquotes"></a>Alıntı blokları

> Kuraklık on milyon yıldır artık görüşmelerin süren ve korkunç saltanatı biteli uzun beri sona erdi. Burada bir gün Afrika olarak bilinecek Kıta Ekvator'un üzerinde Savaşının vahşeti yeni bir climax ulaşmıştı, tamamladı ve kazanan değil henüz belli değildi. Bu çorak ve kurumuş topraklarda yalnızca küçük hızlı veya Vahşi süslü veya hatta hayatta kalabilmenin.

## <a name="images"></a>Görüntüler

### <a name="static-image-or-animated-gif"></a>Statik görüntü veya animasyonlu gif

![Bu alternatif metindir](../images/Logo_DotNet.png)

### <a name="linked-image"></a>Bağlantılı görüntü

[![bağlantılı görüntü için alternatif metin](../images/Logo_DotNet.png)](https://dot.net)

## <a name="videos"></a>Videolar

### <a name="channel-9"></a>Channel 9

[![Larry Osterman - kendi Bill Gates ile bir etkileşim (üzerinden DOS Ağ yığını)](https://sec.ch9.ms/ch9/caf5/f8657a22-5b83-47a3-9748-4c1be9fecaf5/Larry-Osterman-His-one-interaction-with-Bill-Gate_960.jpg)
](https://channel9.msdn.com/Blogs/TheChannel9Team/Larry-Osterman-His-one-interaction-with-Bill-Gates-over-DOS-networking-stack)

### <a name="youtube"></a>YouTube

[![.NET üzerinde 4/2/2016 - Scott Hunter](https://img.youtube.com/vi/g2a4W6Q7aRw/0.jpg)
](https://www.youtube.com/watch?v=g2a4W6Q7aRw)

## <a name="docsmicrosoft-extensions"></a>docs.Microsoft uzantıları

docs.Microsoft, GitHub Flavored Markdown için birkaç ek uzantıları sağlar. 

### <a name="alerts"></a>Uyarılar

Belgeler sitesinde uygun stiliyle işlenen aşağıdaki uyarı stilleri kullanmak önemlidir. Ancak, GitHub üzerinde işleme altyapısı bunları ayırt etmez.

#### <a name="note"></a>Not

> [!NOTE]
> Bu bir nottur

#### <a name="warning"></a>Uyarı

> [!WARNING]
> Bu bir uyarıdır

#### <a name="tip"></a>İpucu

> [!TIP]
> Bu bir ipucudur

#### <a name="important"></a>Önemli

> [!IMPORTANT]
> Bu, önemli örneğidir

Ve şu şekilde işlemesi: ![uyarı stilleri](../images/alerts.png)

### <a name="buttons"></a>Düğmeler

> [!div class="button"]
[Düğme bağlantıları](../docs/core/index.md)

Eylem düğmeleri örneği gördüğünüz [Intune belgeleri](https://docs.microsoft.com/intune/get-started/choose-how-to-enroll-devices). 

### <a name="selectors"></a>Seçici

> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/using-on-windows.md)

Eylem Seçici örneği gördüğünüz [Intune belgeleri](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune#how-your-end-users-get-their-apps).

### <a name="step-by-steps"></a>Adım tarafından adımlar

>[!div class="step-by-step"]
[Öncesi](../docs/csharp/expression-trees-interpreting.md)
[İleri](../docs/csharp/expression-trees-translating.md)

Adım tarafından adımların eylem, örneği gördüğünüz [Advanced Threat Analytics belgeleri](https://docs.microsoft.com/advanced-threat-analytics/deploy-use/install-ata-step2).
