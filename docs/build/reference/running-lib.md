---
title: LıB çalıştırma
description: LIB. exe ile kullanabileceğiniz komut satırı seçeneklerini açıklar.
ms.date: 09/25/2019
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
- Lib
- VC.Project.VCLibrarianTool.PrintProgress
- VC.Project.VCLibrarianTool.SuppressStartupBanner
helpviewer_keywords:
- -MACHINE target platform option
- command files, LIB
- MACHINE target platform option
- colon command files
- VERBOSE library manager option
- /NOLOGO library manager option
- dash option specifier
- /MACHINE target platform option
- forward slash option specifier
- -NOLOGO library manager option
- LIB [C++], running LIB
- -VERBOSE library manager option
- /VERBOSE library manager option
- command files
- NOLOGO library manager option
- slash (/)
- semicolon, command files
- / command files
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
ms.openlocfilehash: 0d65c8d8b3b0cd28c7cccda25bfd9512321172f9
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685549"
---
# <a name="running-lib"></a>LıB çalıştırma

KITAPLıĞı denetlemek için çeşitli komut satırı seçenekleri kullanılabilir.

## <a name="lib-command-line"></a>LıB komut satırı

LıB çalıştırmak için, bunu yapmak için LIB kullandığınız görevin seçeneklerini ve dosya adlarını `lib` komutunu yazın. LıB Ayrıca aşağıdaki bölümde açıklanan komut dosyalarındaki komut satırı girişini de kabul eder. LıB bir ortam değişkeni kullanmaz.

## <a name="lib-command-files"></a>LıB komut dosyaları

Komut satırı bağımsız değişkenlerini aşağıdaki sözdizimini kullanarak bir komut dosyasında LıB 'e geçirebilirsiniz:

> **LIB \@** <em>komut dosyası</em>

Dosya *komutu-dosya* bir metin dosyasıdır. At işareti ( **\@** ) ve dosya adı arasında boşluk veya sekmeye izin verilmez. *Komut dosyası* adının varsayılan uzantısı yoktur; herhangi bir uzantı dahil olmak üzere tam dosya adını belirtmeniz gerekir. Joker karakterler kullanılamaz. Dosya adıyla mutlak veya göreli bir yol belirtebilirsiniz.

Komut dosyasında, komut satırında olabilecek bağımsız değişkenler boşluklarla veya sekmelerle ayrılabilir. Bağımsız değişkenler de yeni satır karakterleri ile ayrılabilir. Bir yorumu işaretlemek için noktalı virgül ( **;** ) kullanın. LıB, noktalı virgülden tüm metni satır sonuna kadar yoksayar.

Komut dosyasının tümünü veya bir kısmını bir komut dosyasında belirtebilir ve bir LIB komutunda birden fazla komut dosyası kullanabilirsiniz. LıB komut dosyası girişini komut satırındaki bu konumda belirtilmiş gibi kabul eder. Komut dosyaları iç içe olamaz. **/Nologo** seçeneği kullanılmadığı takdirde LIB, komut dosyalarının içeriğini yankılar.

## <a name="using-lib-options"></a>LıB seçeneklerini kullanma

Bir seçenek, bir tire ( **-** ) veya eğik çizgi ( **/** ) olan ve ardından seçeneğin adı gelen bir seçenek belirticisinden oluşur. Seçenek adları kısaltılabilir. Bazı seçenekler, iki nokta üst üste ( **:** ) sonra belirtilen bir bağımsız değişken alır. Seçenek belirtimi içinde boşluk veya sekmeye izin verilmez. Komut satırındaki seçenek belirtimlerini ayırmak için bir veya daha fazla boşluk ya da sekme kullanın. Seçenek adları ve bunların anahtar sözcüğü ya da dosya adı bağımsız değişkenleri büyük/küçük harfe duyarlıdır, ancak bağımsız değişken olarak kullanılan tanımlayıcılar büyük/küçük harfe duyarlıdır LıB, seçenekleri komut satırında ve komut dosyalarında belirtilen sırada işler. Bir seçenek farklı bağımsız değişkenlerle tekrarlandığında, işlenecek son değer öncelik kazanır.

Aşağıdaki seçenekler LıB 'in tüm modları için geçerlidir:

> **/Errorreport** \[**yok** &#124; **istem** &#124; **kuyruğu** &#124; **gönderme**]

LIB. exe çalışma zamanında başarısız olursa, bu iç hatalar hakkında Microsoft 'a bilgi göndermek için **/errorreport** ' u kullanabilirsiniz.

**/Errorreport**hakkında daha fazla bilgi için bkz. [/errorreport (Iç derleyici hatalarını raporla)](errorreport-report-internal-compiler-errors.md).

> **/LINKREPRO:** _dizin-yol_ \
> **/LINKREPROTARGET:** _dosya adı_

Microsoft lib. exe kilitlenmelerini ve iç hataları tanılamasına yardımcı olmak için [/LINKREPRO](linkrepro.md) seçeneğini kullanabilirsiniz. Microsoft 'un kitaplık işlemleri sırasında oluşan bir sorunu yeniden oluşturmasına izin veren bir dizi derleme *yapıtı*olan bir bağlantı yeniden üretme işlemi oluşturur. [/LINKREPROTARGET](linkreprotarget.md) seçeneği **/LINKREPRO** seçeneğiyle birlikte kullanılabilir. Yalnızca lib. exe belirtilen dosyayı oluşturduğunda bağlantı yeniden üretme yapıtları oluşturur. Daha fazla bilgi için bkz. [Microsoft C++ araç takımı ile sorun bildirme](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md).

> **/LTCG**

"LTCG", *bağlantı zamanı kod üretimi*için temsil eder. Bu özellik derleyici ([CL. exe](compiler-options.md)), LIB ve bağlayıcı ([bağlantı](linker-options.md)) arasında birlikte işlem gerektirir. böylece, herhangi bir bileşenin kendisi tarafından yapabileceklerinin ötesinde kodu iyileştirebilirsiniz.

LıB için **/LTCG** seçeneği, CL. exe ' den alınan girişlerin [/GL](gl-whole-program-optimization.md) derleyici seçeneği kullanılarak oluşturulan nesne dosyalarını dahil edileceğini belirtir. LıB bu tür girdilerle karşılaşırsa ve **/LTCG** belirtilmemişse, bir bilgi iletisi görüntülendikten sonra/LTCG etkinleştirilmiş olarak yeniden başlatılır. Diğer bir deyişle, bu seçeneği açıkça ayarlamak gerekli değildir, ancak LıB 'in kendisini yeniden başlatması gerektiğinden, bunu yapmak için yapı performansını hızlandırır.

Yapı sürecinde, LıB 'den çıkış BAĞLANTıSı ' na gönderilir. BAĞLANTıNıN kendi ayrı **/LTCG** seçeneği vardır. Tam program iyileştirme ve profil temelli iyileştirme (PGO) araçları dahil çeşitli iyileştirmeler gerçekleştirmek için kullanılır. BAĞLANTı seçeneği hakkında daha fazla bilgi için bkz. [/LTCG](ltcg-link-time-code-generation.md).

> **/MACHıNE**

Program için hedef platformu belirtir. Genellikle, **/Machine**belirtmeniz gerekmez. LıB,. obj dosyalarından makine türünü anlar. Ancak, bazı durumlarda LIB makine türünü belirleyemez ve bir hata mesajı yayınlar. Böyle bir hata oluşursa, **/Machine**' i belirtin. **/Extract** modunda, bu seçenek yalnızca doğrulama içindir. Kullanılabilir makine türlerini görmek için komut satırında `lib /?` kullanın.

> **/NOLOGO**

LıB telif hakkı iletisi ve sürüm numarasını görüntülemeyi engeller ve komut dosyalarının yankısını önler.

> **/VERBOSE**

Eklenmekte olan. obj dosyalarının adları da dahil olmak üzere, oturumun ilerleme durumu hakkındaki ayrıntıları görüntüler. Bilgiler standart çıktıya gönderilir ve bir dosyaya yönlendirilebilir.

> **/WX**[ **: No**]

Uyarıları hata olarak değerlendirin. Daha fazla bilgi için bkz. [/WX (bağlayıcı uyarılarını hata olarak işle)](wx-treat-linker-warnings-as-errors.md).

Diğer seçenekler yalnızca belirli LıB modları için geçerlidir. Bu seçenekler, her bir modu açıklayan bölümlerde ele alınmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[LıB başvurusu](lib-reference.md)
