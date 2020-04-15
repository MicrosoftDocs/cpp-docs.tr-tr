---
title: MSVC bağlayıcı başvurusu
ms.date: 12/10/2018
ms.assetid: bb736587-d13b-4f3c-8982-3cc2c015c59c
ms.openlocfilehash: 2503e212e7325fc97f9057861cb85d5cf0571094
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336495"
---
# <a name="linking"></a>Bağlama

Bir C++ projesinde bağlama *adımı,* derleyici kaynak kodu nesne dosyalarına (*.obj) derledikten sonra gerçekleştirilir. Bağlayıcı (link.exe), nesne dosyalarını tek bir yürütülebilir dosyada birleştirir.

Bağlayıcı seçenekleri Visual Studio içinde veya dışında ayarlanabilir. Visual Studio'da, **Solution Explorer'daki** proje düğümüne sağ tıklayarak ve özellik sayfalarını görüntülemek için **Özellikler'i** seçerek bağlayıcı seçeneklerine erişebilirsiniz. Düğümü genişletmek ve tüm seçenekleri görmek için sol bölmedeki **Bağlayıcı'yı** seçin.

## <a name="linker-command-line-syntax"></a>Bağlayıcı komut satırı sözdizimi

VISUAL Studio dışında LINK çalıştırdığınızda, bir veya daha fazla şekilde giriş belirtebilirsiniz:

- Komut satırında:

- Komut dosyalarını kullanma

- Çevre değişkenlerinde

LINK ilk işlemler seçenekleri LINK ortamı değişkeninde belirtilen, komut satırında ve komut dosyalarında belirtilen sırayla seçenekleri takip eder. Bir seçenek farklı bağımsız değişkenlerle yinelenirse, işlenen son seçenek önce gelir.

Seçenekler tüm yapı için geçerlidir; belirli giriş dosyalarına hiçbir seçenek uygulanamaz.

LINK çalıştırmak için. EXE, aşağıdaki komut sözdizimini kullanın:

```
LINK arguments
```

Seçenekler `arguments` ve dosya adları içerir ve herhangi bir sırada belirtilebilir. Seçenekler önce işlenir, sonra dosyalar. Bağımsız değişkenleri ayırmak için bir veya daha fazla boşluk veya sekme kullanın.

> [!NOTE]
> Bu aracı yalnızca Visual Studio komut isteminden başlatabilirsiniz. Sistem komut isteminden veya Dosya Gezgini'nden başlatamazsınız.

## <a name="command-line"></a>Komut satırı

Komut satırında, bir seçenek, bir satır (-) veya ileri eğik çizgi (/) ve ardından seçeneğin adından gelen bir seçenek belirticisinden oluşur. Seçenek adları kısaltılamaz. Bazı seçenekler, bir üst üste (:) sonra belirtilen bir bağımsız değişken alır. /COMMENT seçeneğinde teklif edilen bir dize dışında, opsiyon belirtimi içinde boşluk veya sekmelere izin verilmez. Ondalık veya C dili gösteriminde sayısal bağımsız değişkenler belirtin. Seçenek adları ve anahtar kelime veya dosya adı bağımsız değişkenleri büyük/küçük harf duyarlı değildir, ancak bağımsız değişkenler olarak tanımlayıcılar büyük/küçük harf duyarlıdır.

Bir dosyayı bağlayıcıya geçirmek için LINK komutundan sonra komut satırındaki dosya adını belirtin. Dosya adı ile mutlak veya göreceli bir yol belirtebilir ve dosya adında joker karakterler kullanabilirsiniz. Nokta (.) ve dosya adı uzantısını atlarsanız, LINK dosyayı bulmak amacıyla .obj'yi varsayar. LINK dosya adı uzantıları veya dosyaların içeriği hakkında varsayımlar yapmak için bunların eksikliği kullanmaz; dosya türünü inceleyerek belirler ve buna göre işler.

link.exe başarı için sıfır döndürür (hata yok).  Aksi takdirde, bağlayıcı bağlantıyı durduran hata numarasını döndürür.  Örneğin, bağlayıcı LNK1104 oluşturursa, bağlayıcı 1104 döndürür.  Buna göre, bağlayıcı tarafından bir hata döndürülen en düşük hata numarası 1000'dir.  128'in geri dönüş değeri, işletim sistemi veya .config dosyasıyla ilgili bir yapılandırma sorununu temsil eder; yükleyici ya link.exe veya c2.dll yüklemedi.

## <a name="link-command-files"></a>LINK Komut Dosyaları

Komut satırı bağımsız değişkenlerini bir komut dosyası biçiminde LINK'e geçirebilirsiniz. Bağlayıcıya bir komut dosyası belirtmek için aşağıdaki sözdizimini kullanın:

> **LINK \@ ** <em>komut dosyası</em>

*Komut dosyası* bir metin dosyasının adıdır. At işareti (**\@**) ile dosya adı arasında boşluk veya sekme izin verilmez. Varsayılan uzantı yoktur; herhangi bir uzantı da dahil olmak üzere tam dosya adını belirtmeniz gerekir. Joker karakterler kullanılamaz. Dosya adı ile mutlak veya göreceli bir yol belirtebilirsiniz. LINK, dosyayı aramak için bir ortam değişkeni kullanmaz.

Komut dosyasında, bağımsız değişkenler boşluklar veya sekmelerle (komut satırında olduğu gibi) ve yeni satır karakterleriyle ayrılabilir.

Komut satırının tamamını veya bir kısmını bir komut dosyasında belirtebilirsiniz. BIR LINK komutunda birden fazla komut dosyası kullanabilirsiniz. LINK komut dosyası girişini komut satırındaki bu konumda belirtilmiş gibi kabul eder. Komut dosyaları iç içe geçemez. [/NOLOGO](nologo-suppress-startup-banner-linker.md) seçeneği belirtilmediği sürece LINK komut dosyalarının içeriğini yansıtır.

## <a name="example"></a>Örnek

Bir DLL oluşturmak için aşağıdaki komut nesne dosyaları ve kitaplıklar ayrı komut dosyalarında adlarını geçer ve / İhRACAT seçeneği belirtimi için üçüncü bir komut dosyası kullanır:

```cmd
link /dll @objlist.txt @liblist.txt @exports.txt
```

## <a name="link-environment-variables"></a>LINK Ortam Değişkenleri

LINK aracı aşağıdaki ortam değişkenlerini kullanır:

- LINK \_ve\_LINK , tanımlanırsa. LINK aracı, LINK ortamında tanımlanan seçenekleri ve bağımsız değişkenleri hazırlar ve işlemeden\_ önce LINK ortamı değişkeninde \_tanımlanan seçenekleri ve bağımsız değişkenleri komut satırı bağımsız değişkenlerine ekler.

- LIB, tanımlanırsa. LINK araçları, komut satırında veya [/BASE](base-base-address.md) seçeneğinde belirtilen bir nesne, kitaplık veya başka bir dosya ararken LIB yolunu kullanır. Ayrıca, bir nesnede adı geçen bir .pdb dosyasını bulmak için LIB yolunu kullanır. LIB değişkeni, yarım kolonlarla ayrılmış bir veya daha fazla yol belirtimi içerebilir. Bir yol Visual C++ yüklemenizin \lib alt dizinini işaret etmelidir.

- PATH, aracın CVTRES çalışması gerekiyorsa ve link kendisi ile aynı dizinde dosyayı bulamıyor. (LINK, CVTRES'in bir .res dosyasını bağlamasını gerektirir.) PATH, Visual C++ yüklemenizin \bin alt dizinini işaret etmelidir.

- TMP, OMF veya .res dosyalarını bağlarken bir dizini belirtmek için.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Bina Referans](c-cpp-building-reference.md)
[ı MSVC Bağlantı Seçenekleri](linker-options.md)
[Modül Tanımı (.def) Gecikme](module-definition-dot-def-files.md)
[Yüklü DL'ler için](linker-support-for-delay-loaded-dlls.md) Dosyalar Bağlayıcı Desteği
