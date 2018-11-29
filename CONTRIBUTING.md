# <a name="contributing"></a>Katkıda bulunan

Visual C++ belgelerine katkıda bulunan İlginiz için teşekkür ederiz!

Bu konu başlığında, ekleme veya içeriği güncelleştirmek için temel işlemi göreceğiniz [Visual C++ belge sitesine](https://docs.microsoft.com/cpp).

Bu konu başlığında, şu konulara değineceğiz:

* [Katkıda bulunmak için işlem](#process-for-contributing)
* [Gerekenler ve yapılmaması gerekenler](#dos-and-donts)
* [Belgeleri oluşturma](#building-the-docs)
* [Örneklerine katkıda bulunan](#contributing-to-samples)
* [Katkıda bulunan lisans sözleşmesi](#contributor-license-agreement)

## <a name="process-for-contributing"></a>Katkıda bulunmak için işlem

**1. adım:** yazmak istediğiniz makale ve varolan içeriği nasıl ilişkili olduğunu açıklayan bir sorun açın.
İçindeki içeriği **docs** klasöre (örneğin, hata ayıklayıcı) içerik alanı tarafından düzenlenir bölümlere düzenlenir. Yeni içeriğinizi doğru klasörünü anlamaya çalışın. Teklifiniz hakkında geri bildirim alın.

Küçük değişiklikler için ilk bu adımı atlayabilirsiniz.

**2. adım:** çatal `MicrosoftDocs/cpp-docs` depo.

**3. adım:** oluşturma bir `branch` makale için.

**4. adım:** Makalenizi yazın.

Yeni bir konu varsa bunu kullanabilirsiniz [şablon dosyası](./styleguide/template.md) , başlangıç noktası olarak. Bu yazma yönergeleri içerir ve ayrıca Yazar bilgileri gibi her bir makaleyi için gerekli meta veriler açıklanmaktadır.

1. adımda makale için belirlenen TOC konuma karşılık gelen klasörüne gidin.
Bu klasör için bu bölümdeki tüm makaleleri Markdown dosyalarını içerir. Gerekirse, içerik için dosyaları yerleştirmek için yeni bir klasör oluşturun.

Görüntüleri ve diğer statik kaynaklar için bunları adlı alt klasöre Ekle `media`. İçerik için yeni bir klasör oluşturuyorsanız, bir medya klasörüne yeni klasöre ekleyin.

Uygun Markdown söz dizimini takip ettiğinizden emin olun. Bkz: [Stil Kılavuzu](./styleguide/template.md) daha fazla bilgi için.

### <a name="example-structure"></a>Örnek yapısı

    docs
        /standard-library
            wstring-convert-class.md
            /media
                wstring-conversion.png

**5. adım:** bir çekme isteği (PR) için kendi dalınızdaki gönderme `MicrosoftDocs/cpp-docs/master`.

Çekme isteğiniz var olan bir sorunu ele alıyor mu yoksa ekleyin `Fixes #Issue_Number` anahtar sözcüğü işleme iletisi veya çekme isteği açıklaması, böylece çekme isteği birleştirilirken sorunu otomatik olarak kapatılabilir. Daha fazla bilgi için [işleme iletileri aracılığıyla sorunlarına kapatma](https://help.github.com/articles/closing-issues-via-commit-messages/).

Visual Studio team Çekme isteğiniz gözden geçirin ve değişikliğin iyi görünüyor ya da onaylamak için gerekli diğer güncelleştirmeleri/değişiklikleri varsa bildiren.

**6. adım:** ekiple açıklandığı gibi gerekli güncelleştirmeleri dalınızda olun.

Maintainers Çekme değişikliğiniz iyi görünüyor ve geri bildirim uygulandıktan sonra ana dal ile birleştirilecek.

Belirli bir bir temposu üzerinde biz tüm işlemeleri ana daldan Canlı dalına gönderin ve ardından canlı katkılarınız görmek mümkün olacaktır [docs.microsoft.com](https://docs.microsoft.com/cpp/).

## <a name="dos-and-donts"></a>Gerekenler ve yapılmaması gerekenler

.NET belgelerine katkıda bulunuyorsanız, dikkat etmeniz gereken kuralların yönlendirmede, kısa bir listesi aşağıdadır.

- **Yoksa** bize büyük çekme istekleriyle beklenmedik. Bunun yerine, bir sorunu oluşturun ve büyük miktarda zaman yatırım önce bir yönü kabul edebilir, böylece bir tartışma başlatın.
- **YAPMAK** okuma [Stil Kılavuzu](./styleguide/template.md) ve [ses ve sesi](./styleguide/voice-tone.md) yönergeleri.
- **YAPMAK** kullanın [şablon](./styleguide/template.md) dosyası iş başlangıç noktası olarak.
- **YAPMAK** makalelerde çalışmaya başlamadan önce çatalınızdaki ayrı bir dal oluşturun.
- **YAPMAK** izleyin [GitHub akışı iş akışı](https://guides.github.com/introduction/flow/).
- **YAPMAK** blog ve tweet (veya ne olursa olsun) Katkılarınızı, sık!

> [!NOTE]
> Konuların bazıları burada belirtilen şu anda tüm yönergeleri izleyerek ve üzerinde olduğunu fark edebilirsiniz [Stil Kılavuzu](./styleguide/template.md) de. Site genelinde tutarlılık elde etmeye yönelik çalışıyoruz. Listesini kontrol edin [açık sorun](https://github.com/MicrosoftDocs/cpp-docs/issues?q=is%3Aissue+is%3Aopen+label%3Aguidelines-adherence) biz şu anda bu belirli bir hedef için takip ettiğiniz.

## <a name="building-the-docs"></a>Belgeleri oluşturma

Belgelere yazılan [GitHub Flavored Markdown](https://help.github.com/categories/writing-on-github/) ve kullanılarak oluşturulan [DocFX](https://dotnet.github.io/docfx/) ve diğer iç yayımlama/yapı araçları. Konumunda barındırılan [docs.microsoft.com](https://docs.microsoft.com/).

Docs yerel olarak derlemek istediğiniz yüklemek gerekirse [DocFX](https://dotnet.github.io/docfx/); en son en iyi sürümleridir.

DocFX kullanmak için birkaç yolu vardır ve çoğu, kapsamdaki [DocFX Başlarken Kılavuzu](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html). Aşağıdaki yönergeleri kullanın [komut satırı tabanlı](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html#2-use-docfx-as-a-command-line-tool) aracı sürümü. Bağlantıyı yukarıda listelenen yollar ile deneyimliyseniz, bunları kullanmaktan çekinmeyin.

**Not:** şu anda DocFX, .NET Framework üzerinde Windows ya da Mono (Linux veya macOS) gerektirir. .NET Core için gelecekte bağlantı noktasına umuyoruz.

Derleme ve yerleşik web sunucusu kullanılarak yerel olarak elde edilen site Önizleme. Gidin `cpp-docs\docs` klasör makinesindeki ve aşağıdaki komutu yazın:

> docfx -t varsayılan--hizmet

Bu yerel Önizleme başlatır [8080](http://localhost:8080). Ardından, giderek değişiklikleri görüntüleyebilirsiniz `http://localhost:8080/[path]`, gibi `http://localhost:8080/cpp/visual-cpp-in-visual-studio.html`.

**Not:** görünümünü belgeler sitesinde olduğu gibi aynı olmayacaktır yerel önizlemede şu anda tüm tema şu anda içermiyor. Bu deneyimi düzeltme doğrultusunda çalışıyoruz. Ayrıca bazı özel uzantılar videodur, notlar ve önizlemede görünmeyecektir dahil edilen belgeler, için kullanırız.

## <a name="contributing-to-samples"></a>Örneklerine katkıda bulunan

Şu an için gerekli örnek kod, makaledeki satır içi kod blokları olarak içerir. Depoya sahip bir `codesnippets` klasör, ancak bu genel katkılar için hazır değil.

## <a name="contributor-license-agreement"></a>Katkıda bulunan lisans sözleşmesi

Oturum açmanız gerekir [katılım Lisans Sözleşmesi (CLA)](LICENSE) Çekme isteğiniz birleştirilmeden önce. Bu, docs.microsoft.com projeleri için tek seferlik bir gereksinimdir. Daha fazla bilgi edinebilirsiniz [katkı lisans sözleşmeleri'ni (CLA)](https://en.wikipedia.org/wiki/Contributor_License_Agreement) wikipedia.

Ön sözleşme imzalayan gerekmez. Kopyalama, çatalı ve her zaman olduğu gibi çekme isteği gönderin. Çekme isteğiniz oluşturulduğunda, CLA botu tarafından sınıflandırılır. Değişiklik Önemsiz değilse (örneğin, bir yazım yanlışı sabit), ardından çekme isteği CLA-not-gerekli ile etiketlenir. Aksi takdirde, CLA gerekli olarak sınıflandırılır. CLA imzalandıktan sonra güncel ve gelecekteki tüm çekme isteklerini CLA imzalı olarak etiketlenir.
