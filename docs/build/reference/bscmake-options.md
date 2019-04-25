---
title: BSCMAKE Seçenekleri
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCBscMakeTool.OutputFile
- VC.Project.VCBscMakeTool.SuppressStartupBanner
- VC.Project.VCBscMakeTool.PreserveSBR
helpviewer_keywords:
- /v BSCMAKE option
- Iu BSCMAKE option
- browse information files (.bsc), content
- /Er BSCMAKE option
- NOLOGO BSCMAKE option
- /s BSCMAKE option
- /Ei BSCMAKE option
- /o BSCMAKE option
- /NOLOGO BSCMAKE option
- /Iu BSCMAKE option
- s BSCMAKE option (/s)
- /Em BSCMAKE option
- Em BSCMAKE option
- Es BSCMAKE option
- files [C++], BSCMAKE
- Er BSCMAKE option
- BSCMAKE, options for controlling files
- controlling BSCMAKE options
- El BSCMAKE option
- /El BSCMAKE option
- /Es BSCMAKE option
- Ei BSCMAKE option
ms.assetid: fa2f1e06-c684-41cf-80dd-6a554835ebd2
ms.openlocfilehash: b1d62e8d122cb4f08feef60d6936359b3e246749
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272877"
---
# <a name="bscmake-options"></a>BSCMAKE Seçenekleri

> [!WARNING]
> BSCMAKE hala Visual Studio ile yüklenir ancak artık IDE tarafından kullanılır. Visual Studio 2008'den itibaren göz atma ve sembol bilgilerini otomatik olarak bir SQL Server .sdf dosyası çözüm klasöründe depolanır.

Bu bölümde, BSCMAKE denetlemek için kullanılabilen seçenekler açıklanmaktadır. Çeşitli seçenekler gözatma bilgisi dosyası içeriğini hariç veya belirli bilgiler dahil olmak üzere denetler. Dışlama seçenekleri BSCMAKE daha hızlı çalışmasına izin verebilir ve daha küçük bir .bsc dosyasına neden olabilir. Seçenek adlarını büyük küçük harfe duyarlı (dışında **/HELP** ve **/nologo**).

Yalnızca **/nologo** ve **/o** Visual Studio geliştirme ortamında kullanılabilir.  Bkz: [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md) hakkında bilgi için bir projenin özellik sayfalarındaki erişim.

**/Ei (** *filename*... **)**<br/>
Belirlenen içerme dosyalarının içeriğini gözatma bilgileri dosyasını hariç tutar. Birden çok dosyayı belirtmek için adlarının boşlukla ayırın ve liste parantez içine. Parantezler yalnızca birini belirtirseniz gerekli olmayan *filename*. Kullanım **/Ei** ile birlikte **/Es** dosyaları tarafından dışarıda tutma seçeneği **/Es**.

**/El**<br/>
Yerel semboller dışlar. Yerel simgeler dahil etmek için varsayılandır. Yerel simgeler hakkında daha fazla bilgi için bkz. [bir .sbr dosyası oluşturma](creating-an-dot-sbr-file.md).

**/Em**<br/>
Semboller makroları gövdesinde dışlar. Kullanım **/Em** makro adları yalnızca gözatma bilgileri dosyasına eklenecek. Makro adları hem de makro genişletmeleri sonucu eklemek için varsayılandır.

**/Er (** *sembol*... **)**<br/>
Belirtilen simgeler gözatma bilgileri dosyasını hariç tutar. Birden fazla sembol adlarını belirtmek için adlarının boşlukla ayırın ve liste parantez içine. Parantezler yalnızca birini belirtirseniz gerekli olmayan *sembol*.

**/ES**<br/>
Gözatma bilgileri dosyasından INCLUDE ortam değişkeninde belirtilen mutlak bir yol bulunamadı veya mutlak bir yol ile belirtilen her dahil etme dosyasını hariç tutar. (Sistem genellikle bunlar birçok göz atma bilgisi dosyanıza gerekmeyebilir bilgi içeren dosyaları içerir.) Bu seçenek, belirtilen bir yol olmadan veya göreli yolları ya da dahil etme göreli bir yolunda bulunan dosyaları ile dosyaları dışarıda değil. Kullanabileceğiniz **/Ei** seçeneği ile birlikte **/Es** dışlanacak dosyalar **/Es** hariç tutmaz. Yalnızca bazı dosyaları dışarıda bırakmak istiyorsanız, **/Es** hariç kullanın **/Ei** yerine **/Es** ve hariç tutmak istediğiniz dosyaları listeleyebilirsiniz.

**/errorreport:**[**none** &#124; **prompt** &#124; **queue** &#124; **send**]<br/>
Bscmake.exe iç hatalara ilişkin bilgileri Microsoft'a sağlar.

Daha fazla bilgi için **/errorreport**, bkz: [/errorreport (dahili derleme hatalarını raporla)](errorreport-report-internal-compiler-errors.md).

**/HELP**<br/>
BSCMAKE komut satırı sözdizimi özetini görüntüler.

**/IU**<br/>
Başvurulmayan semboller içerir. Varsayılan olarak tanımlandı ancak başvurulmayan semboller BSCMAKE kaydetmez. .Sbr dosyası paketlenmiş, derleyici başvurulmayan semboller zaten kaldırıldığından bu seçeneği, giriş dosyası için etkisi yoktur.

**/n**<br/>
Artımlı olmayan bir derleme zorlar. Kullanım **/n** .bsc dosyası olup olmadığı mevcut gözatma bilgisi dosyası tam bir derlemesini zorlamak için ve .sbr dosyaları kesildi gelen önlemek için. Bkz: [BSCMAKE .bsc dosyasını nasıl derler](how-bscmake-builds-a-dot-bsc-file.md).

**/ NOLOGO**<br/>
BSCMAKE telif hakkı iletisini görüntüler.

**/o** *dosya adı*<br/>
Gözatma bilgisi dosyası için bir ad belirtir. Varsayılan olarak, BSCMAKE gözatma bilgisi dosyası birinci .sbr dosyası ve .bsc uzantısı temel adı sağlar.

**/S (** *filename*... **)**<br/>
BSCMAKE belirlenen içerme dosyasına, karşılaşılan ilk kez işlemek ve aksi takdirde dışlanacak söyler. Bir dosya (örneğin, bir üst bilgi veya .h, dosya için bir .c veya .cpp kaynak dosyasının) birkaç kaynak dosyalarına dahil edilen ancak yönergeleri her zaman ön işleme tarafından değiştirilmez durumlarda işleme zaman kazanmak için bu seçeneği kullanın. Oluşturmakta olduğunuz gözatma bilgisi dosyası için önemli olan yollarla bir dosya değiştirildiğinde, bu seçeneği kullanmak isteyebilirsiniz. Birden çok dosyayı belirtmek için adlarının boşlukla ayırın ve liste parantez içine. Parantezler yalnızca birini belirtirseniz gerekli olmayan *filename*. Dahil edilen her zaman dosyanın hariç tutmak istiyorsanız kullanın **/Ei** veya **/Es** seçeneği.

**/v**<br/>
İşlenmekte olan her .sbr dosyası adı ve tam BSCMAKE çalıştırma hakkında bilgi içeren ayrıntılı çıkış sağlar.

**/?**<br/>
BSCMAKE komut satırı sözdizimi kısa bir özetini görüntüler.

BSCMAKE üç .sbr dosyaları MAIN.bsc tam bir derlemesini yapmak için şu komut satırını belirtir. Ayrıca, yinelenen uyarı örneklerini TOOLBOX.h dışlanacak BSCMAKE bildirir:

```
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr
```

## <a name="see-also"></a>Ayrıca bkz.

[BSCMAKE Başvurusu](bscmake-reference.md)
