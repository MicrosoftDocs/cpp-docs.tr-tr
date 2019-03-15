---
title: MSVC bağlayıcı başvurusu
ms.date: 12/10/2018
ms.assetid: bb736587-d13b-4f3c-8982-3cc2c015c59c
ms.openlocfilehash: 3a9eebef0a264b0131311b5ca96011a4d56264a1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820383"
---
# <a name="linking"></a>Bağlama

Bir C++ projesinde *bağlama* derleyici kaynak kodu (*.obj) nesne dosyalarına hazırladığı sonra adım gerçekleştirilir. Bağlayıcı (link.exe) nesne dosyalarına tek bir yürütülebilir dosya birleştirir. 

Bağlayıcı seçenekleri içinde veya Visual Studio dışında ayarlayabilirsiniz. Visual Studio içinde bağlayıcı Seçenekleri'nde proje düğümüne sağ tıklayarak erişim **Çözüm Gezgini** seçip **özellikleri** özellik sayfaları görüntülemek için. Seçin **bağlayıcı** düğümünü genişletin ve tüm seçenekleri görmek için sol bölmedeki. 


## <a name="linker-command-line-syntax"></a>Bağlayıcı komut satırı sözdizimi

Visual Studio dışında bağlantı çalıştırdığınızda Giriş bir veya daha fazla şekilde belirtebilirsiniz:

- Komut satırında:

- Komut dosyalarını kullanma

- Ortam değişkenleri

İlk işlem seçeneklerinin bağlantı seçenekleri komut satırında belirtilen bunlar sırada ve komut dosyaları tarafından izlenen bağlantı ortam değişkeninde belirtilen. Bir seçenek farklı bağımsız değişkenler yinelenirse işlediği son olaydan önceliklidir.

Seçenekler, tüm derleme için geçerlidir; belirli bir giriş dosyaları için seçenekleri uygulanabilir.

BAĞLANTI çalıştırılacak. EXE, aşağıdaki komut söz dizimini kullanın:

```
LINK arguments
```

`arguments` Seçenekleri ve dosya adları içerir ve herhangi bir sırada belirtilebilen. Seçenekler şunlardır: ilk işlenen, sonra da dosyaları. Bir veya daha fazla boşluk veya sekme bağımsız değişkenleri ayırmak için kullanın.

> [!NOTE]
>  Bu araç yalnızca Visual Studio komut isteminden başlatabilirsiniz. Bir sistem komut satırından veya dosya Gezgini'nden başlatılamıyor.

## <a name="command-line"></a>Komut satırı

Komut satırında bir seçenek bir seçenek belirleyicisinden oluşur. bir tire (-) veya eğik çizgi (/) seçeneğinin adı tarafından izlenen. Seçenek adları kısaltılmış olamaz. Bazı seçenekler bir iki nokta (:) sonra belirtilen bir bağımsız değişken alan. Boşluk veya sekme bir seçenek belirtimi içinde dışında/Comment seçeneğinde alıntılanmış dize içinde izin verilir. Ondalık veya C dili gösterimi sayısal bağımsız değişkenleri belirtin. Seçenek adları ve anahtar sözcüğü veya dosya adı bağımsız değişkenler büyük küçük harfe duyarlı değildir, ancak bağımsız değişken olarak tanımlayıcıları büyük küçük harf duyarlıdır.

Bağlayıcı için bir dosya geçirmek için dosya adı bağlantı komutundan sonra komut satırında belirtin. Mutlak veya göreli bir yol ile dosya adını belirtin ve dosya adında joker karakterler kullanabilirsiniz. Nokta (.) ve dosya adı uzantısı atlarsanız, bağlantı .obj dosyası bulma amacıyla varsayar. BAĞLANTI eksikliği veya dosya adı uzantıları dosyaların içeriği hakkında varsayımlar yapmak kullanmaz; Dosya türü, inceleyerek belirler ve buna göre işler.

Link.exe başarı durumunda (hatasız) sıfır döndürür.  Aksi takdirde bağlayıcı bağlantı durduruldu hata numarasını döndürür.  Örneğin, bağlayıcı LNK1104 oluşturursa, bağlayıcı 1104 döndürür.  Buna göre bir hatada bağlayıcı tarafından döndürülen en düşük hata sayısı 1000'dir.  128 dönüş değeri bir yapılandırma sorunu işletim sisteminde veya .config dosyasını temsil eder; Yükleyici link.exe ya da c2.dll yüklenmedi.

## <a name="link-command-files"></a>LINK Komut Dosyaları

Komut satırı bağımsız değişkenleri, bir komut dosyası biçiminde bağlantıya geçirebilirsiniz. Bağlayıcı için bir komut dosyası belirtmek için aşağıdaki sözdizimini kullanın:

> **Bağlantı \@**  <em>commandfile</em>

*Commandfile* bir metin dosyasının adıdır. Hiçbir boşluk veya sekme arasında izin at işareti (**\@**) ve dosya adı. Hiçbir varsayılan uzantı yoktur; herhangi bir uzantısına dahil olmak üzere tam dosya adı belirtmeniz gerekir. Joker karakterler kullanılamaz. Mutlak veya göreli bir yol ile dosya adını belirtebilirsiniz. BAĞLANTI, dosyayı aramak için bir ortam değişkeni kullanmaz.

Komut dosyasında bağımsız değişkenleri tarafından boşluk veya sekme (komut satırında gibi) ayrılabilir ve yeni satır karakterleri.

Komut satırının bir kısmını veya tamamını bir komut dosyasında belirtebilirsiniz. Birden fazla komut dosyasında bir LINK komutunu kullanabilirsiniz. Komut satırında o konumda belirtildi alacağı bağlantı komut dosyası girişi kabul eder. Komut dosyaları iç içe olamaz. BAĞLANTI yankılayan komut dosyalarının içeriğini sürece [/nologo](nologo-suppress-startup-banner-linker.md) seçeneği belirtildi.

## <a name="example"></a>Örnek

Bir DLL yapılandırmak için aşağıdaki komutu ayrı komut dosyaları nesne dosyaları ve kitaplıkları adlarını geçirir ve kullanır, dosya/EXPORTS seçeneğinin belirtimi için üçüncü komut:

```cmd
link /dll @objlist.txt @liblist.txt @exports.txt
```

## <a name="link-environment-variables"></a>LINK Ortam Değişkenleri

Bağlantı aracını aşağıdaki ortam değişkenleri kullanır:

- BAĞLANTI ve \_bağlantı\_, tanımlı değilse. BAĞLANTI araç seçenekleri ve bağlantı ortam değişkeninde tanımlanan değişkenleri ekler ve seçenekleri ekler ve bağımsız değişkenler tanımlanan \_bağlantı\_ işlemeden önce komut satırı bağımsız değişkenleri ortam değişkeni.

- LIB, tanımlı değilse. BAĞLANTI araçları, bir nesne, kitaplık veya komut satırında ya da belirtilen başka bir dosya ararken LIB yolunu kullanır [/BASE](base-base-address.md) seçeneği. Ayrıca bir nesnedeki adlı bir .pdb dosyası bulmak için LIB yolunu kullanır. LIB değişkeni, noktalı virgülle ayrılmış bir veya daha fazla yol özellikleri içerebilir. Bir yol, Visual C++ yüklemenizin \lib alt dizinine işaret etmelidir.

- YOL, aracın CVTRES çalıştırmaya gerek duymadığı ve bağlantının kendisi ile aynı dizinde dosya bulunamıyor. (Bağlantı CVTRES bir .res dosyası bağlamanız gerekir.) YOL, Visual C++ yüklemenizin \bin alt dizinine işaret etmelidir.

- TMP, OMF veya .res dosyaları bağlanırken bir dizin belirtmek için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ oluşturma başvurusu](c-cpp-building-reference.md)
[MSVC bağlayıcı seçenekleri](linker-options.md)
[modül-tanımlama (.def) dosyaları](module-definition-dot-def-files.md)
[için bağlayıcı desteği Gecikmeli yüklenen DLL'ler](linker-support-for-delay-loaded-dlls.md)
