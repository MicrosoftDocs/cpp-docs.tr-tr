---
title: BSCMAKE Seçenekleri
description: Microsoft BSCMAKE yardımcı programı komut satırı seçeneklerine başvuru.
ms.date: 02/09/2020
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
ms.openlocfilehash: f0fd0e01d3325267ac175435aab65b5d0a9d47ea
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257799"
---
# <a name="bscmake-options"></a>BSCMAKE Seçenekleri

> [!WARNING]
> BSCMAKE, Visual Studio ile hala yüklü olsa da artık IDE tarafından kullanılmıyor. Visual Studio 2008 ' den itibaren, gezinme ve sembol bilgileri çözüm klasöründeki bir SQL Server *`.sdf`* dosyasında otomatik olarak depolanır.

Bu bölümde BSCMAKE 'i denetlemek için kullanılabilen seçenekler açıklanmaktadır. Bazı seçenekler, belirli bilgileri dışlayarak veya dahil olmak üzere, tarama bilgileri dosyasının içeriğini denetler. Dışlama seçenekleri BSCMAKE 'in daha hızlı çalışmasına izin verebilir ve daha küçük bir *`.bsc`* dosyası oluşmasına neden olabilir. Seçenek adları büyük/küçük harfe duyarlıdır ( **/help** ve **/nologo**hariç).

Yalnızca **/nologo** ve **/O** , Visual Studio geliştirme ortamı içinden kullanılabilir.  Projenin özellik sayfalarına erişim hakkında bilgi için bkz. [Visual Studio 'da derleyici ve derleme özelliklerini ayarlama C++ ](../working-with-project-properties.md) .

**/Ei (** _dosya adı_... **)** \
Belirtilen içerme dosyalarının içeriğini, tarama bilgileri dosyasından dışlar. Birden çok dosya belirtmek için, adları boşlukla ayırın ve listeyi parantez içine alın. Yalnızca bir *dosya adı*belirtirseniz parantezler gerekli değildir. **/Es tarafından dışlanan**dosyaları dışlamak için **/es** seçeneğiyle birlikte **/ei** kullanın.

**/El**\
Yerel sembolleri dışlar. Varsayılan, yerel sembolleri dahil etmek için kullanılır. Yerel semboller hakkında daha fazla bilgi için bkz [. sbr dosyası oluşturma](creating-an-dot-sbr-file.md).

**/Em**\
Makrolar gövdesinde sembolleri dışlar. **/Em** ' i, yalnızca tarama bilgileri dosyasındaki makroların adlarını içerecek şekilde kullanın. Varsayılan değer, hem makro adlarını hem de makro genişleimleri sonucunu dahil etmek için kullanılır.

**/Er (** _sembol_... **)** \
Belirtilen sembolleri, tarama bilgileri dosyasından dışlar. Birden çok sembol adı belirtmek için, adları boşlukla ayırın ve listeyi parantez içine alın. Yalnızca bir *sembol*belirtirseniz parantezler gereksizdir.

**/Es**\
Mutlak bir yol ile belirtilen tüm içerme dosyalarını dışlar veya ıNCLUDE ortam değişkeninde belirtilen mutlak bir yolda bulunur. (Genellikle, bu dosyalar, gözatmanıza ilişkin bilgi dosyanızda gerek duyabileceği çok fazla bilgi içeren sistem içerme dosyalarıdır.) Bu seçenek, yol olmadan veya göreli yollarla belirtilen dosyaları ya da ıNCLUDE içindeki göreli bir yolda bulunan dosyaları dışmaz. /Es 'nin dışlanmaz dosyaları dışlamak için **/es** ile birlikte **/ei** seçeneğini de kullanabilirsiniz. Dosyaların yalnızca bir kısmını dışlamak istiyorsanız, **/es**yerine **/ei** kullanın ve dışlamak istediğiniz dosyaları listeleyin.

**/errorreport:** [**none** &#124; **Prompt** &#124; **kuyruğu** &#124; **gönderme**] \
Bu seçenek kullanım dışıdır. Windows Vista 'Dan başlayarak hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir.

**/Help**\
BSCMAKE komut satırı sözdiziminin özetini görüntüler.

**/Iu**\
Başvurulmayan sembolleri içerir. Varsayılan olarak, BSCMAKE tanımlanmış ancak başvurulmayan sembolleri kaydetmez. Bir *`.sbr`* dosyası paketlenmışsa, derleyici başvurulmayan sembolleri zaten kaldırmış olduğundan bu seçeneğin bu giriş dosyası için bir etkisi yoktur.

**/n**\
Artımlı olmayan bir derlemeyi zorlar. *`.bsc`* bir dosyanın var olup olmadığını ve *`.sbr`* dosyalarının kesilip kesilmeyeceğini engellemek için, **/n** kullanın. Bkz. [BSCMAKE,. bsc dosyasını nasıl oluşturur](how-bscmake-builds-a-dot-bsc-file.md).

**/Nologo**\
BSCMAKE telif hakkı iletisini bastırır.

**/o** *dosya adı*\
Tarama bilgisi dosyası için bir ad belirtir. Varsayılan olarak, BSCMAKE, gözden geçirme bilgileri dosyasına ilk *`.sbr`* dosyanın temel adı ve *`.bsc`* uzantısı sağlar.

**/S (** _dosya adı_... **)** \
BSCMAKE 'in belirtilen içerme dosyasını ilk kez karşılaştığı şekilde işlemesini ve aksi halde dışlanmasını söyler. Bir dosya (örneğin, bir üstbilgi veya *`.h`* , bir *`.c`* veya *`.cpp`* kaynak dosyası için dosya) birkaç kaynak dosyasına dahil edildiğinde, ancak her seferinde ön işleme yönergeleri tarafından değişmeden kaldığı zaman işleme süresini kaydetmek için bu seçeneği kullanın. Oluşturmakta olduğunuz tarama bilgisi dosyası için önemli olmayan yollarla bir dosya değiştirilirse bu seçeneği kullanın. Birden çok dosya belirtmek için, adları boşlukla ayırın ve listeyi parantez içine alın. Yalnızca bir *dosya adı*belirtirseniz parantezler gerekli değildir. Dosyayı her eklendiğinde dışlamak istiyorsanız, **/ei** veya **/es** seçeneğini kullanın.

**/v**\
İşlenen her *`.sbr`* dosyanın adını ve tüm BSCMAKE çalıştırması hakkında bilgi içeren ayrıntılı çıkış sağlar.

**/?** \
BSCMAKE komut satırı sözdiziminin kısa bir özetini görüntüler.

Aşağıdaki komut satırı, BSCMAKE 'in üç *`.sbr`* dosyadan MAIN. bsc 'nin tam derlemesini yapmayı söyler. Ayrıca BSCMAKE 'in yinelenen araç kutusu. h örneklerini dışlanmasını söyler. h:

```cmd
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr
```

## <a name="see-also"></a>Ayrıca bkz.

[BSCMAKE Başvurusu](bscmake-reference.md)
