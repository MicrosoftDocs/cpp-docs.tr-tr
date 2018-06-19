---
title: ML ve ML64 komut satırı başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: da3fb143aeaaf6fa8cf31c45b31707fa01bf6898
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057805"
---
# <a name="ml-and-ml64-command-line-reference"></a>ML ve ML64 Komut Satırı Başvurusu
Derler ve bir veya daha fazla assembly dili kaynak dosyaları bağlar. Komut satırı seçenekleri büyük/küçük harfe duyarlıdır.  
  
 Ml64.exe hakkında daha fazla bilgi için bkz: [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ML [[options]] filename [[ [[options]]  filename]]  
ML64 [[options]] filename [[ [[options]]  filename]]  
...  
[[/link linkoptions]]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `options`  
 Aşağıdaki tabloda listelenen seçenekleri.  
  
|Seçenek|Eylem|  
|------------|------------|  
|**/AT**|Bellek modeli küçük desteği sağlar. .Com biçimi dosyaları gereksinimlerini ihlal kod yapıları için hata iletileri sağlar. Bu eşdeğer olduğunu unutmayın [. MODEL](../../assembler/masm/dot-model.md) **çok küçük** yönergesi.<br /><br /> Ml64.exe kullanılamaz.|  
|**/Bl** `filename`|Alternatif bir bağlayıcı seçer.|  
|**/c**|Yalnızca derler. Bağlantı vermiyor.|  
|**/ coff**|Genel nesne dosya biçimi (COFF) türünde nesne modülü oluşturur. Genellikle Win32 assembly dili geliştirme için gereklidir.<br /><br /> Ml64.exe kullanılamaz.|  
|**/CP**|Tüm kullanıcı tanımlayıcıları durumunun korur.|  
|**/Cu**|Tüm kimliklerin büyük harf (varsayılan) eşler.<br /><br /> Ml64.exe kullanılamaz.|  
|**/Cx**|Ortak ve extern sembolleri durumda korur.|  
|**/D** `symbol`[[=`value`]]|Verilen ada sahip bir metin makrosu tanımlar. Varsa `value` olan eksik, boş olur. Boşluklarla ayırarak birden çok belirteç tırnak işaretleri içine alınmalıdır.|  
|**/EP**|Önceden işlenmiş kaynak listesini (STDOUT'a gönderilen) oluşturur. Bkz: **/Sf**.|  
|**/ ERRORREPORT** [ **NONE** &AMP;#124; **KOMUT İSTEMİ** &AMP;#124; **SIRA** &AMP;#124; **GÖNDER** ]|Çalışma zamanında ML.exe veya ml64.exe başarısız olursa, kullanabileceğiniz **/errorreport** iç bu hatalar hakkında bilgi göndermek için.<br /><br /> Hakkında daha fazla bilgi için **/errorreport**, bkz: [/errorreport (dahili derleme hatalarını raporla)](../../build/reference/errorreport-report-internal-compiler-errors.md).|  
|**/F** `hexnum`|Ayarlar yığın boyutu `hexnum` bayt (Bu aynıdır **/bağlantı/yığın**:`number`). Değer onaltılık gösterimde ifade edilmesi gerekir. Arasında bir boşluk olmalıdır **/F** ve `hexnum`.|  
|**/FE** `filename`|Yürütülebilir dosya adı.|  
|**/Fl**[[`filename`]]|Birleştirilmiş kod listesi oluşturur. Bkz: **/Sf**.|  
|**/FM**[[`filename`]]|Bir bağlayıcı eşleme dosyası oluşturur.|  
|**/FO** `filename`|Bir nesne dosya adı. Daha fazla bilgi için Açıklamalar bölümüne bakın.|  
|**/ FPi**|Öykünücü onarımların kayan nokta aritmetik (yalnızca karma dil) için oluşturur.<br /><br /> Ml64.exe kullanılamaz.|  
|**/FR**[[`filename`]]|Kaynak tarayıcı .sbr dosyası oluşturur.|  
|**/FR**[[`filename`]]|Kaynak tarayıcı .sbr dosyası, genişletilmiş bir form oluşturur.|  
|**/GC**|Çağırma ve adlandırma kuralları FORTRAN veya Pascal stil işlev kullanımını belirtir. Aynı **seçeneği dil: PASCAL**.<br /><br /> Ml64.exe kullanılamaz.|  
|**/Gd**|Çağırma ve adlandırma kuralları C tarzı işlevi kullanımını belirtir. Aynı **seçeneği dil: C**.<br /><br /> Ml64.exe kullanılamaz.|  
|**/GZ**|Çağırma ve adlandırma kuralları __stdcall işlevi kullanımını belirtir.  Aynı **seçeneği dil: STCALL**.<br /><br /> Ml64.exe kullanılamaz.|  
|**/H** `number`|Dış adlar sayı önemli karakterler için sınırlar. Varsayılan 31 karakterdir.<br /><br /> Ml64.exe kullanılamaz.|  
|**/ Help**|ML hakkında Yardım için QuickHelp çağırır.|  
|**/I** `pathname`|İçerme dosyası yolunu ayarlar. En fazla 10 **/I** seçenekleri izin verilir.|  
|**/nologo**|Başarılı derleme iletileri gizler.|  
|**/ OMF**|Nesne modülü dosya biçimi (OMF) nesne modül türünü oluşturur.  **/ OMF** gelir **/c**; ML.exe OMF nesnelerini bağlamanın desteklemez.<br /><br /> Ml64.exe kullanılamaz.|  
|**/SA**|Kullanılabilir tüm bilgiler listesi üzerinde etkinleştirir.|  
|**SAFESEH**|Nesne hiçbir özel durum işleyicileri içeren ya da içeren tüm ile bildirilen özel durum işleyicileri olarak işaretler [. SAFESEH](../../assembler/masm/dot-safeseh.md).<br /><br /> Ml64.exe kullanılamaz.|  
|**/SF**|İlk geçişi listesi için döküm dosyası ekler.|  
|**/SL** `width`|Satır başına karakter listeleme kaynak çizgi genişliğini ayarlar. Aralık 60-255 veya 0 değil. Varsayılan 0'dır. Aynı [sayfa](../../assembler/masm/page.md) genişliği.|  
|**/Sn**|Bir liste üretirken sembol tablosunu devre dışı bırakır.|  
|**/SP** `length`|Sayfa başına satır listeleme kaynak sayfası uzunluğunu belirler. Aralık 10-255 veya 0 değil. Varsayılan 0'dır. Aynı [sayfa](../../assembler/masm/page.md) uzunluğu.|  
|**/Ss** `text`|Kaynak liste metnini belirtir. Aynı [ALTYAZISI](../../assembler/masm/subtitle.md) metin.|  
|**/St** `text`|Kaynak liste başlığı belirtir. Aynı [başlık](../../assembler/masm/title.md) metin.|  
|**/SX**|Listesindeki false koşulları açar.|  
|**/Ta** `filename`|Kaynak dosyanın adı .asm uzantısı ile bitmez derler.|  
|**/w**|Aynı **/W0/WX**.|  
|**/W** `level`|Uyarı düzeyi ayarlar nerede `level` = 0, 1, 2 veya 3.|  
|**/WX**|Uyarılar üreten bir hata kodu döndürür.|  
|**/X**|INCLUDE ortam yolu yok sayın.|  
|**/Zd**|Satır numarası bilgilerini nesne dosyasına oluşturur.|  
|**/ZF**|Tüm sembolleri genel hale getirir.|  
|**/Zi**|CodeView bilgilerini nesne dosyasına oluşturur.|  
|**/Zm**|Etkinleştirir**M510** MASM 5.1 ile en fazla Uyumluluk seçeneği.<br /><br /> Ml64.exe kullanılamaz.|  
|**/Zp**[[`alignment`]]|Yapıları belirtilen bayt sınırında paketleri. `alignment` 1, 2 veya 4 olabilir.|  
|**/ZS**|Yalnızca sözdizimi denetimi gerçekleştirir.|  
|**/?**|ML komut satırı sözdizimi özetini görüntüler.|  
  
 `filename`  
 Dosyanın adı.  
  
 `linkoptions`  
 Bağlantı seçenekleri.  Bkz: [bağlayıcı seçenekleri](../../build/reference/linker-options.md) daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 ML ve ML64 komut satırı bazı seçenekleri yerleştirme duyarlıdır. Örneğin, ML ve ML64 birkaç kabul edebilirsiniz çünkü **/c** seçenekleri, tüm karşılık gelen **/Fo** seçenekleri belirtilen, önce **/c**. Aşağıdaki komut satırı örnek her derleme dosya belirtimi için bir nesne dosya belirtimini gösterilmektedir:  
  
 **ML.exe /Fo a1.obj /c a.asm /Fo b1.obj /c b.asm**  
  
## <a name="environment-variables"></a>Ortam Değişkenleri  
  
|Değişken|Açıklama|  
|--------------|-----------------|  
|INCLUDE|INCLUDE dosyalar için arama yolu belirtir.|  
|ML|Varsayılan komut satırı seçeneklerini belirtir.|  
|TMP|Geçici dosyalar için yolunu belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ML hata iletileri](../../assembler/masm/ml-error-messages.md)   
 [Microsoft Macro Assembler Başvurusu](../../assembler/masm/microsoft-macro-assembler-reference.md)