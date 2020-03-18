---
title: LIB Çalıştırma
description: LIB. exe ile kullanabileceğiniz komut satırı seçeneklerini açıklar.
ms.date: 02/09/2020
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
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
ms.openlocfilehash: 871b92809f38b4dcbf84de802b1ac9940ea6f1e9
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438942"
---
# <a name="running-lib"></a>LIB Çalıştırma

KITAPLıĞı denetlemek için çeşitli komut satırı seçenekleri kullanılabilir.

## <a name="lib-command-line"></a>LıB komut satırı

LıB çalıştırmak için, komut `lib`yazın ve ardından LıB kullandığınız görevin seçeneklerini ve dosya adlarını yazın. LıB Ayrıca aşağıdaki bölümde açıklanan komut dosyalarındaki komut satırı girişini de kabul eder. LıB bir ortam değişkeni kullanmaz.

## <a name="lib-command-files"></a>LıB komut dosyaları

Komut satırı bağımsız değişkenlerini aşağıdaki sözdizimini kullanarak bir komut dosyasında LıB 'e geçirebilirsiniz:

> **LIB \@** <em>komut dosyası</em>

Dosya *komutu-dosya* bir metin dosyasıdır. At işareti ( **\@** ) ve dosya adı arasında boşluk veya sekmeye izin verilmez. *Komut dosyası* adının varsayılan uzantısı yok. Herhangi bir uzantı dahil olmak üzere tam dosya adını belirtin. Joker karakterler kullanılamaz. Dosya adıyla mutlak veya göreli bir yol belirtebilirsiniz.

Komut dosyasında, komut satırında olabilecek bağımsız değişkenler boşluklarla veya sekmelerle ayrılabilir. Bağımsız değişkenler de yeni satır karakterleri ile ayrılabilir. Bir yorumu işaretlemek için noktalı virgül ( **;** ) kullanın. LıB, noktalı virgülden tüm metni satır sonuna kadar yoksayar.

Komut dosyasının tümünü veya bir kısmını bir komut dosyasında belirtebilir ve bir LIB komutunda birden fazla komut dosyası kullanabilirsiniz. LıB komut dosyası girişini komut satırındaki bu konumda belirtilmiş gibi kabul eder. Komut dosyaları iç içe olamaz. **/Nologo** seçeneği kullanılmadığı takdirde LIB, komut dosyalarının içeriğini yankılar.

## <a name="using-lib-options"></a>LıB seçeneklerini kullanma

Bir seçenek, bir tire ( **-** ) veya eğik çizgi ( **/** ) ve ardından seçeneğin adı olan bir seçenek belirticisinden oluşur. Seçenek adları kısaltılabilir. Bazı seçenekler, iki nokta üst üste ( **:** ) sonra belirtilen bir bağımsız değişken alır. Seçenek belirtimi içinde boşluk veya sekmeye izin verilmez. Komut satırındaki seçenek belirtimlerini ayırmak için bir veya daha fazla boşluk ya da sekme kullanın. Seçenek adları ve bunların anahtar sözcüğü ya da dosya adı bağımsız değişkenleri büyük/küçük harfe duyarlıdır, ancak bağımsız değişken olarak kullanılan tanımlayıcılar büyük/küçük harfe duyarlıdır LıB, seçenekleri komut satırında ve komut dosyalarında belirtilen sırada işler. Bir seçenek farklı bağımsız değişkenlerle tekrarlandığında, işlenecek son değer öncelik kazanır.

Aşağıdaki seçenekler LıB 'in tüm modları için geçerlidir:

> **/Errorreport** \[**hiçbir** &#124; **istem** &#124; **kuyruğunu** &#124; **Gönder**]

/ERRORREPORT seçeneği kullanım dışıdır. Windows Vista 'Dan başlayarak hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir.

> **/LINKREPRO:** _dizin-yol_ \
> **/LINKREPROTARGET:** _dosya adı_

Microsoft lib. exe kilitlenmelerini ve iç hataları tanılamasına yardımcı olmak için [/LINKREPRO](linkrepro.md) seçeneğini kullanabilirsiniz. Bu seçenek, Microsoft 'un kitaplık işlemleri sırasında oluşan bir sorunu yeniden oluşturmasına izin veren bir dizi derleme *yapıtı*olan bir bağlantı yeniden oluşturma işlemi oluşturur. [/LINKREPROTARGET](linkreprotarget.md) seçeneği **/LINKREPRO** seçeneğiyle birlikte kullanılabilir. Yalnızca lib. exe belirtilen dosyayı oluşturduğunda bağlantı yeniden üretme yapıtları oluşturur. Daha fazla bilgi için bkz. [Microsoft C++ araç takımı ile sorun bildirme](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md).

> **/LTCG**

"LTCG", *bağlantı zamanı kod üretimi*için temsil eder. Bu özellik derleyici ([CL. exe](compiler-options.md)), LIB ve bağlayıcı ([bağlantı](linker-options.md)) arasında birlikte işlem gerektirir. Birlikte, herhangi bir bileşenin kendisi tarafından yapabileceklerinin ötesinde kodu iyileştirebilirler.

**/LTCG** seçeneği LIB, CL. exe ' den alınan girişlerin [/GL](gl-whole-program-optimization.md) derleyici seçeneği kullanılarak oluşturulan nesne dosyalarını içermesini belirtir. LıB bu tür girdilerle karşılaşırsa ve **/LTCG** belirtilmemişse, bir bilgi iletisi görüntülendikten sonra/LTCG etkinken yeniden başlatılır. Diğer bir deyişle, bu seçeneği açıkça ayarlamak gerekli değildir, ancak derleme performansını hızlandırır. Bunun nedeni, LıB 'in kendisini yeniden başlatması gerekmez.

Yapı sürecinde, LıB 'den çıkış BAĞLANTıSı ' na gönderilir. BAĞLANTıNıN kendi ayrı **/LTCG** seçeneği vardır. Tam program iyileştirme ve profil temelli iyileştirme (PGO) araçları dahil çeşitli iyileştirmeler gerçekleştirmek için kullanılır. BAĞLANTı seçeneği hakkında daha fazla bilgi için bkz. [/LTCG](ltcg-link-time-code-generation.md).

> **/MACHıNE**

Program için hedef platformu belirtir. Genellikle, **/Machine**belirtmeniz gerekmez. LıB,. obj dosyalarından makine türünü anlar. Ancak, bazı durumlarda LIB makine türünü belirleyemez ve bir hata mesajı yayınlar. Böyle bir hata oluşursa, **/Machine**' i belirtin. **/Extract** modunda, bu seçenek yalnızca doğrulama içindir. Kullanılabilir makine türlerini görmek için komut satırındaki `lib /?` kullanın.

> **/NOLOGO**

LıB telif hakkı iletisi ve sürüm numarasını görüntülemeyi engeller ve komut dosyalarının yankısını önler.

> **/VERBOSE**

Eklenmekte olan. obj dosyalarının adları da dahil olmak üzere, oturumun ilerleme durumu hakkındaki ayrıntıları görüntüler. Bilgiler standart çıktıya gönderilir ve bir dosyaya yönlendirilebilir.

> **/WX**[ **: No**]

Uyarıları hata olarak değerlendirin. Daha fazla bilgi için bkz. [/WX (bağlayıcı uyarılarını hata olarak işle)](wx-treat-linker-warnings-as-errors.md).

Diğer seçenekler yalnızca belirli LıB modları için geçerlidir. Bu seçenekler, her bir modu açıklayan bölümlerde ele alınmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[LIB Başvurusu](lib-reference.md)
