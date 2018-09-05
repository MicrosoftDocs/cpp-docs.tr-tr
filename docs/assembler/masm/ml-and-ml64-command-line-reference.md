---
title: ML ve ML64 komut satırı başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ML
dev_langs:
- C++
helpviewer_keywords:
- /W* MASM compiler option
- /c MASM compiler option
- /EP MASM compiler option
- /Fe MASM compiler option
- /Zp MASM compiler option
- /AT MASM compiler option
- /Zm MASM compiler option
- /Sf MASM compiler option
- /Sp MASM compiler option
- /w MASM compiler option
- /Fl MASM compiler option
- /coff MASM compiler option
- /St MASM compiler option
- /Cx MASM compiler option
- /Sl MASM compiler option
- /Cu MASM compiler option
- MASM (Microsoft Macro Assembler), ML command-line reference
- /FPi MASM compiler option
- /Zf MASM compiler option
- ML environment variable
- /Fr MASM compiler option
- /help MASM compiler option
- /Sa MASM compiler option
- /Zd MASM compiler option
- /I MASM compiler option
- /? MASM compiler option
- /Bl MASM compiler option
- /Fm MASM compiler option
- /Fo MASM compiler option
- command-line reference [ML]
- /Sn MASM compiler option
- /Gd MASM compiler option
- /D* MASM compiler option
- environment variables, ML
- /Gc MASM compiler option
- /F* MASM compiler option
- /Sc MASM compiler option
- /H MASM compiler option
- /Zs MASM compiler option
- /omf MASM compiler option
- /Sg MASM compiler option
- /Cp MASM compiler option
- /Zi MASM compiler option
- /nologo MASM compiler option
- /Sx MASM compiler option
- /WX MASM compiler option
- /Ss MASM compiler option
- command line, reference [ML]
- /Ta MASM compiler option
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41d3603bc09b7c63fdd152e1c7d5921c2bb3eb7c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693409"
---
# <a name="ml-and-ml64-command-line-reference"></a>ML ve ML64 Komut Satırı Başvurusu

Derler ve bir veya daha fazla kaynak dosyaları derleme dili bağlar. Komut satırı seçenekleri büyük/küçük harfe duyarlıdır.

Ml64.exe hakkında daha fazla bilgi için bkz. [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="syntax"></a>Sözdizimi

> ML [[*seçenekleri*]] *filename* [[[[*seçenekleri*]] *filename*]]

> ML64 [[*seçenekleri*]] *filename* [[[[*seçenekleri*]] *filename*]]... [[/ link *linkoptions*]]

### <a name="parameters"></a>Parametreler

*Seçenekler*<br/>
Aşağıdaki tabloda listelenen seçenekleri.

|Seçenek|Eylem|
|------------|------------|
|**/AT**|Bellek modeli küçük desteği sağlar. .Com biçimi dosyaları gereksinimlerini ihlal kod yapıları için hata iletileri sağlar. Bu eşdeğer olduğunu unutmayın [. MODEL](../../assembler/masm/dot-model.md) **çok küçük** yönergesi.<br /><br /> Ml64.exe kullanılamaz.|
|**/Bl** *dosya adı*|Alternatif bir bağlayıcı seçer.|
|**/c**|Yalnızca birleştirir. Bağlantı vermiyor.|
|**/ coff**|Ortak nesne dosyası biçimi (COFF) türünde nesne modülü oluşturur. Genellikle Win32 derleme dili geliştirme için gereklidir.<br /><br /> Ml64.exe kullanılamaz.|
|**/CP**|Tüm kullanıcı tanımlayıcılarını durumu korur.|
|**/Cu**|Tüm büyük harfe (varsayılan) eşleştirir.<br /><br /> Ml64.exe kullanılamaz.|
|**/Cx**|Genel ve extern sembolleri durumda korur.|
|**/D** *sembol*[[=*değer*]]|Belirtilen ada sahip bir metin makro tanımlar. Varsa *değer* olan eksik, boş olur. Boşluklarla ayırarak birden çok belirteç tırnak içine alınmalıdır.|
|**/EP**|Önceden işlenmiş kaynak listesini (STDOUT'a gönderilen) oluşturur. Bkz: **/Sf**.|
|**/ ERRORREPORT** [ **NONE** &AMP;#124; **İSTEMİ** &AMP;#124; **KUYRUK** &AMP;#124; **GÖNDER** ]|ML.exe veya ml64.exe çalışma zamanında başarısız olursa, kullanabileceğiniz **/errorreport** iç bu hataları hakkında Microsoft'a bilgi göndermek.<br /><br /> Hakkında daha fazla bilgi için **/errorreport**, bkz: [/errorreport (dahili derleme hatalarını raporla)](../../build/reference/errorreport-report-internal-compiler-errors.md).|
|**/F** *hexnum*|Yığın boyutunu ayarlar *hexnum* bayt (aynı budur **/bağlantı/STACK**:*numarası*). Değeri, onaltılık gösterimde ifade edilmelidir. Arasına bir boşluk olması gerekir **/F** ve *hexnum*.|
|**/FE** *dosya adı*|Yürütülebilir dosyanın adı.|
|**/Fl**[[*filename*]]|Bir birleştirilmiş kod listesi oluşturur. Bkz: **/Sf**.|
|**/FM**[[*filename*]]|Bir bağlayıcı haritası dosyası oluşturur.|
|**/FO** *dosya adı*|Bir nesne dosyası adı. Daha fazla bilgi için Açıklamalar bölümüne bakın.|
|**/ FPi**|Öykünücü onarımların için kayan nokta aritmetiği (yalnızca karma dil) oluşturur.<br /><br /> Ml64.exe kullanılamaz.|
|**/FR**[[*filename*]]|Kaynak tarayıcı .sbr dosyası oluşturur.|
|**/FR**[[*filename*]]|Kaynak tarayıcı .sbr dosyası, genişletilmiş bir form oluşturur.|
|**/GC**|Arama ve adlandırma kuralları FORTRAN veya Pascal stili işlevi belirtir. Aynı **seçeneği dil: PASCAL**.<br /><br /> Ml64.exe kullanılamaz.|
|**/Gd**|C stili işlevinin çağrılmasını ve adlandırma kuralları belirtir. Aynı **seçeneği dil: C**.<br /><br /> Ml64.exe kullanılamaz.|
|**/GZ**|Arama ve adlandırma kuralları __stdcall işlevi belirtir.  Aynı **seçeneği dil: STCALL**.<br /><br /> Ml64.exe kullanılamaz.|
|**/H** *numarası*|Dış adlar sayı önemli karakterleri kısıtlar. Varsayılan 31 karakterdir.<br /><br /> Ml64.exe kullanılamaz.|
|**/ Help**|ML konusunda Yardım QuickHelp çağırır.|
|**/I** *yol adı*|İçerme dosyası yolunu ayarlar. En fazla 10 **/I** seçenekleri izin verilir.|
|**/nologo**|Başarılı derleme için iletilerinin bastırır.|
|**/ OMF**|Nesne modülü dosya biçimi (OMF) türü nesne modülü oluşturur.  **/ OMF** gelir **/c**; OMF nesnelerini bağlamanın ML.exe desteklemez.<br /><br /> Ml64.exe kullanılamaz.|
|**/SA**|Tüm mevcut bilgileri listesi üzerinde kapatır.|
|**SAFESEH**|Nesne içeren hiçbir özel durum işleyicileri ya da içeren tüm ile bildirilen özel durum işleyicileri olarak işaretler [. SAFESEH](../../assembler/masm/dot-safeseh.md).<br /><br /> Ml64.exe kullanılamaz.|
|**/SF**|İlk geçişli listeleme için listeleme dosyası ekler.|
|**/SL** *genişliği*|Kaynak karakter her satırda listeleme çizgi genişliği ayarlar. 60 ile 255 arasında ya da 0 rozsah. Varsayılan 0'dır. Aynı [sayfa](../../assembler/masm/page.md) genişliği.|
|**/Sn**|Bir liste üretirken sembol tablosu devre dışı bırakır.|
|**/SP** *uzunluğu*|Sayfa başına satırlarda listeleyen kaynak sayfası uzunluğunu ayarlar. Aralığı 10 ila 255 veya 0 ' dir. Varsayılan 0'dır. Aynı [sayfa](../../assembler/masm/page.md) uzunluğu.|
|**/SS** *metin*|Kaynak listesi metnini belirtir. Aynı [alt konu BAŞLIĞINI](../../assembler/masm/subtitle.md) metin.|
|**/St** *metin*|Kaynak liste başlığını belirtir. Aynı [başlık](../../assembler/masm/title.md) metin.|
|**/SX**|False koşullular listesinde açar.|
|**/Ta** *dosya adı*|Kaynak dosya adı .asm uzantısıyla sonlanmıyor birleştirir.|
|**/w**|Aynı **/W0/WX**.|
|**/W** *düzeyi*|Uyarı seviyesini ayarlar burada *düzeyi* = 0, 1, 2 veya 3.|
|**/WX**|Uyarılar üreten bir hata kodu döndürür.|
|**/X**|Ortam yoluna yoksayın.|
|**/Zd**|Satır numarası bilgisi nesne dosyasında oluşturur.|
|**/ZF**|Tüm semboller, genel yapar.|
|**/Zi**|Nesne dosyasında CodeView bilgisi oluşturur.|
|**/Zm**|Sağlar**M510** MASM 5.1 ile en fazla uyumluluk için seçeneği.<br /><br /> Ml64.exe kullanılamaz.|
|**/ZP**[[*hizalama*]]|Belirtilen bayt sınırlarında yapıları paketler. *Hizalama* 1, 2 veya 4 olabilir.|
|**/ZS**|Yalnızca sözdizimi denetimi gerçekleştirir.|
|**/?**|ML komut satırı sözdizimi özetini görüntüler.|

*Dosya adı*<br/>
Dosyanın adı.

*linkoptions*<br/>
Bağlantı seçenekleri.  Bkz: [bağlayıcı seçenekleri](../../build/reference/linker-options.md) daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

ML ve ML64 komut satırı bazı seçenekler yerleştirme duyarlıdır. Örneğin, ML ve ML64 birkaç kabul edebilir çünkü **/c** seçenekleri varsa buna karşılık gelen **/Fo** seçenekleri belirtilen, önce **/c**. Aşağıdaki komut satırı örneği her derleme dosyası belirtimi için bir nesne dosyası belirtimi gösterilmektedir:

**ML.exe /Fo a1.obj /c a.asm /Fo b1.obj /c b.asm**

## <a name="environment-variables"></a>Ortam Değişkenleri

|Değişken|Açıklama|
|--------------|-----------------|
|INCLUDE|Dosyaları eklemek için arama yolunu belirtir.|
|ML|Varsayılan komut satırı seçeneklerini belirtir.|
|TMP|Geçici dosyalar yolunu belirtir.|

## <a name="see-also"></a>Ayrıca bkz.

[ML Hata İletileri](../../assembler/masm/ml-error-messages.md)<br/>
[Microsoft Macro Assembler Başvurusu](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>