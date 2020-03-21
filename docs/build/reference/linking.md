---
title: MSVC bağlayıcı başvurusu
ms.date: 12/10/2018
ms.assetid: bb736587-d13b-4f3c-8982-3cc2c015c59c
ms.openlocfilehash: d46874b5eaff889834df284ba90e6c6f196d8d66
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079508"
---
# <a name="linking"></a>Bağlama

Bir C++ projede, derleyici kaynak kodu nesne dosyalarına (*. obj) derledikten sonra *bağlama* adımı gerçekleştirilir. Bağlayıcı (LINK. exe) nesne dosyalarını tek bir yürütülebilir dosyada birleştirir.

Bağlayıcı seçenekleri, Visual Studio 'nun içinde veya dışında ayarlanabilir. Visual Studio 'da, bağlayıcı seçeneklerine **Çözüm Gezgini** ' de bir proje düğümüne sağ tıklayıp **Özellikler** ' i seçerek özellik sayfalarını görüntüleyin. Düğümü genişletmek ve tüm seçenekleri görmek için sol bölmedeki **bağlayıcı** ' ı seçin.

## <a name="linker-command-line-syntax"></a>Bağlayıcı komut satırı sözdizimi

BAĞLANTıYı Visual Studio dışında çalıştırdığınızda, girişi bir veya daha fazla şekilde belirtebilirsiniz:

- Komut satırında:

- Komut dosyalarını kullanma

- Ortam değişkenlerinde

BAĞLANTı ortamı değişkeninde belirtilen ilk işlem seçeneklerini BAĞLAYıN, ardından Seçenekler, komut satırında ve komut dosyalarında belirtildikleri sırayla belirlenir. Bir seçenek farklı bağımsız değişkenlerle yinelenirse, işlenen son bir öncelik alır.

Tüm derleme için seçenekler geçerlidir; belirli giriş dosyalarına hiçbir seçenek uygulanamaz.

BAĞLANTıSıNı çalıştırmak için. EXE, aşağıdaki komut sözdizimini kullanın:

```
LINK arguments
```

`arguments` seçenekler ve dosya adları içerir ve herhangi bir sırada belirtilebilir. Seçenekler önce ve ardından dosyalar işlenir. Bağımsız değişkenleri ayırmak için bir veya daha fazla boşluk veya sekme kullanın.

> [!NOTE]
>  Bu aracı yalnızca Visual Studio komut isteminden başlatabilirsiniz. Bunu bir sistem komut isteminden veya dosya Gezgini 'nden başlatamazsınız.

## <a name="command-line"></a>Komut satırı

Komut satırında bir seçenek, bir seçenek belirticisinin, tire (-) veya eğik çizgi (/) ve ardından seçeneğin adı ile oluşur. Seçenek adları kısaltılabilir. Bazı seçenekler, iki nokta üst üste (:)) sonra belirtilen bir bağımsız değişken alır. Bir seçenek belirtiminde,/COMMENT seçeneğinde tırnak içine alınmış bir dize dışında boşluk veya sekmeye izin verilmez. Decimal veya C dili gösteriminde sayısal bağımsız değişkenler belirtin. Seçenek adları ve bunların anahtar sözcük veya dosya adı bağımsız değişkenleri büyük/küçük harfe duyarlıdır

Bağlayıcıya bir dosya geçirmek için, bağlantı komutundan sonra komut satırında dosya adını belirtin. Dosya adında mutlak veya göreli bir yol belirtebilirsiniz ve dosya adında joker karakter kullanabilirsiniz. Nokta (.) ve dosya adı uzantısını atlarsanız, bağlantı, dosyayı bulmak amacıyla. obj olarak varsayılır. BAĞLANTı, dosyaların içeriğiyle ilgili varsayımlar yapmak için dosya adı uzantıları veya bunların olmaması; dosyayı inceleyerek dosya türünü belirler ve uygun şekilde işler.

LINK. exe başarılı (hata yok) için sıfır döndürüyor.  Aksi takdirde, bağlayıcı bağlantıyı durduran hata numarasını döndürür.  Örneğin, bağlayıcı LNK1104 oluşturursa bağlayıcı 1104 döndürür.  Buna uygun olarak, bağlayıcı tarafından bir hatada döndürülen en düşük hata numarası 1000 ' dir.  128 dönüş değeri, işletim sistemi ya da. config dosyası ile bir yapılandırma sorununu temsil eder; Yükleyici, LINK. exe veya C2. dll dosyasını yüklemedi.

## <a name="link-command-files"></a>LINK Komut Dosyaları

Komut satırı bağımsız değişkenlerini bir komut dosyası biçiminde bağlantı altına geçirebilirsiniz. Bağlayıcıya bir komut dosyası belirtmek için aşağıdaki sözdizimini kullanın:

> **\@** <em>commandfile</em> 'ı bağla

*Commandfile* , bir metin dosyasının adıdır. At işareti ( **\@** ) ve dosya adı arasında boşluk veya sekmeye izin verilmez. Varsayılan uzantı yoktur; herhangi bir uzantı dahil olmak üzere tam dosya adını belirtmeniz gerekir. Joker karakterler kullanılamaz. Dosya adıyla mutlak veya göreli bir yol belirtebilirsiniz. BAĞLANTı, dosyayı aramak için bir ortam değişkeni kullanmaz.

Komut dosyasında, bağımsız değişkenler boşluklarla veya sekmelerle (komut satırında olduğu gibi) ve yeni satır karakterlerine göre ayrılabilir.

Komut satırının tamamını veya bir kısmını bir komut dosyasında belirtebilirsiniz. Bir bağlantı komutunda birden fazla komut dosyası kullanabilirsiniz. BAĞLANTı, komut dosyası girişini komut satırındaki bu konumda belirtilmiş gibi kabul eder. Komut dosyaları iç içe geçirilemez. [/Nologo](nologo-suppress-startup-banner-linker.md) seçeneği belirtilmediği takdirde, komut dosyalarının içeriğini YANKı altına bağlayın.

## <a name="example"></a>Örnek

DLL oluşturmak için aşağıdaki komut, nesne dosyalarının ve kitaplıklarının adlarını ayrı komut dosyalarında geçirir ve/dışarı aktarmalar seçeneğinin belirtimi için bir üçüncü komut dosyası kullanır:

```cmd
link /dll @objlist.txt @liblist.txt @exports.txt
```

## <a name="link-environment-variables"></a>LINK Ortam Değişkenleri

BAĞLANTı aracı aşağıdaki ortam değişkenlerini kullanır:

- Tanımlandıysa ve bağlantı\_\_. BAĞLANTı aracı, bağlantı ortamı değişkeninde tanımlanan seçenekleri ve bağımsız değişkenleri ekler ve \_LINK\_ ortam değişkeninde tanımlanan seçenekleri ve bağımsız değişkenleri işlemeden önce komut satırı bağımsız değişkenlerine ekler.

- Eğer tanımlanmışsa LIB. BAĞLANTı araçları, komut satırında veya [/Base](base-base-address.md) seçeneğinde belirtilen bir nesne, kitaplık veya diğer bir dosyayı ararken LIB yolunu kullanır. Ayrıca, nesnesinde adlı bir. pdb dosyasını bulmak için LIB yolunu da kullanır. LıB değişkeni, noktalı virgülle ayrılmış bir veya daha fazla yol belirtimi içerebilir. Bir yol, görsel C++ yüklemenizin \lib alt dizinine işaret etmelidir.

- YOL, aracın CVTRES 'yi çalıştırması gerekiyorsa ve dosyayı bağlantı kendisiyle aynı dizinde bulamadıysanız. (Bağlantı, bir. res dosyasını bağlamak için CVTRES gerektirir.) YOL, görsel C++ yüklemenizin \bin alt dizinine işaret etmelidir.

- TMP, OMF veya. res dosyalarını bağlarken bir dizin belirtmek için.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ](c-cpp-building-reference.md)
[MSVC bağlayıcı seçenekleri](linker-options.md)
[modül tanım (. def) dosyaları](module-definition-dot-def-files.md)
, [Gecikmeli yüklenen dll 'Ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md) olan C/oluşturma başvurusu
