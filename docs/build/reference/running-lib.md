---
title: LIB çalıştırma | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
- Lib
- VC.Project.VCLibrarianTool.PrintProgress
- VC.Project.VCLibrarianTool.SuppressStartupBanner
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff75c149ff3cfff5a360314386cc4828d00f4e8d
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894609"
---
# <a name="running-lib"></a>LIB Çalıştırma

LIB denetlemek için çeşitli komut satırı seçenekleri kullanılabilir.

## <a name="lib-command-line"></a>LIB komut satırı

LIB çalıştırmak için komut türü `lib` seçenekleri ve dosya adları görev için gerçekleştirmek için LIB kullanıyorsunuz. LIB, ayrıca aşağıdaki bölümde açıklanan komut dosyalarında komut satırı girişi kabul eder. LIB ortam değişkeni kullanır.

> [!NOTE]
> LINK32.exe için alışkın oldukları ve LIB32.exe Microsoft Win32 Yazılım Geliştirme Seti için Windows NT ile ya da komut kullanmakta olduğunuz sağlanan araçları `link32 -lib` ya da komut `lib32` kitaplıklarını yönetme ve oluşturma kitaplıkları içeri aktarma. Kullanılacak derleme görevleri dosyalarını ve toplu iş dosyaları değiştirdiğinizden emin olun `lib` yerine komutu.

## <a name="lib-command-files"></a>LIB komut dosyaları

Komut satırı bağımsız değişkenleri için aşağıdaki sözdizimini kullanarak bir komut dosyasındaki LIB geçirebilirsiniz:

> **LIB \@**  <em>commandfile</em>

Dosya *commandfile* bir metin dosyasıdır. Hiçbir boşluk veya sekme arasında izin at işareti (**\@**) ve dosya adı. Hiçbir varsayılan uzantı yoktur; herhangi bir uzantısına dahil olmak üzere tam dosya adı belirtmeniz gerekir. Joker karakterler kullanılamaz. Mutlak veya göreli bir yol ile dosya adını belirtebilirsiniz.

Komut satırında geliştiricilerimizin mümkün olduğunca komut dosyasında boşluk veya sekme ile bağımsız değişkenleri ayrılabilir; Yeni satır karakterleriyle da ayrılabilir. Bir yorum işaretlemek için noktalı virgül (;) kullanın. LIB satırın sonuna noktalı virgülden tüm metni yok sayar.

Tüm veya komut satırının bir parçası bir komut dosyası belirtebilirsiniz ve LIB komutunun içinde birden fazla komut dosyası kullanabilirsiniz. Komut satırında o konumda belirtildi, LIB komut dosyası girişi kabul eder. Komut dosyaları iç içe olamaz. / Nologo seçeneği kullanılmadığı sürece LIB komut dosyalarının içeriğini görüntülemektedir.

## <a name="using-lib-options"></a>LIB seçeneklerini kullanma

İsteğe bağlı bir tire (-) ya da seçenek adından önce gelen bir eğik çizgi (/), bir seçenek belirticisi oluşur. Seçenek adları kısaltılmış olamaz. Bazı seçenekler bir iki nokta (:) sonra belirtilen bir bağımsız değişken alan. Boşluk veya sekme içinde bir seçenek belirtimine izin verilir. Komut satırı seçeneği belirtimlerine ayırmak için bir veya daha fazla boşluk veya sekme kullanın. Seçenek adları ve kendi anahtar sözcük veya dosya adı bağımsız değişkenler büyük küçük harfe duyarlı değildir, ancak bağımsız değişken olarak kullanılan tanımlayıcıları büyük/küçük harfe duyarlıdır. LIB seçenekleri komut satırında belirtilen sırada ve komut dosyaları işler. Bir seçenek farklı bağımsız değişkenler yinelenirse işlenecek sonuncu önceliklidir.

Aşağıdaki seçenekler, LIB tüm modları için geçerlidir:

> **/ ERRORREPORT** [**NONE** &AMP;#124; **İSTEMİ** &AMP;#124; **KUYRUK** &AMP;#124; **GÖNDER**]

Lib.exe çalışma zamanında başarısız olursa, bu iç hataları hakkında Microsoft'a bilgi/errorreport kullanabilirsiniz.

/ Errorreport hakkında daha fazla bilgi için bkz: [/errorreport (dahili derleme hatalarını raporla)](../../build/reference/errorreport-report-internal-compiler-errors.md).

> **/LTCG**

Bağlama zamanı kod oluşturmayı kullanarak oluşturulacak kitaplığı neden olur.  Daha fazla bilgi için [/LTCG](../../build/reference/ltcg-link-time-code-generation.md).

> **/ MACHINE**

Program için hedef platformu belirtir. Genellikle, / Machine belirtmeniz gerekmez. LIB .obj dosyaları makine türünden çıkarır. Ancak, bazı durumlarda, LIB makine türü belirlenemiyor ve bir hata iletisi verir. Böyle bir hata oluşursa/Machine belirtin. / Extract modda, yalnızca doğrulama için bu seçeneği değil. Kullanım `lib /?` kullanılabilir makine türlerini görmek için komut satırına.

> **/ NOLOGO**

LIB telif hakkı iletisi ve sürüm numarasını görüntülenmesini engeller ve komut dosyaları Yankı önler.

> **/ VERBOSE**

Eklenen .obj dosya adlarını dahil olmak üzere, oturumunun ilerleme durumu hakkında ayrıntıları görüntüler. Bilgiler Standart çıkışa gönderilir ve bir dosyaya yönlendirilebilir.

> **/WX**[**: NO**]

Uyarıları hata olarak değerlendir. Bkz: [/WX (Bağlayıcı uyarıları hata olarak değerlendir)](../../build/reference/wx-treat-linker-warnings-as-errors.md) daha fazla bilgi için.

Diğer seçenekler, yalnızca belirli modları LIB için geçerlidir. Bu seçeneklerden her modu açıklayan bölümlerde ele alınmıştır.

## <a name="see-also"></a>Ayrıca Bkz.

[LIB Başvurusu](../../build/reference/lib-reference.md)