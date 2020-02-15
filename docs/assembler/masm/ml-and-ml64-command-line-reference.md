---
title: ML ve ML64 komut satırı başvurusu
description: Microsoft Masz ML ve ML64 assembler komut satırı seçeneklerine yönelik başvuru kılavuzu.
ms.date: 02/09/2020
f1_keywords:
- ML
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
ms.openlocfilehash: b5c5a79417cb141da3d5cfe1c08aa39e02a9c7c2
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257370"
---
# <a name="ml-and-ml64-command-line-reference"></a>ML ve ML64 komut satırı başvurusu

Bir veya daha fazla derleme dili kaynak dosyasını ayrıştırır ve bağlar. Komut satırı seçenekleri büyük/küçük harfe duyarlıdır.

Ml64. exe hakkında daha fazla bilgi için bkz. [x64 Için ması (ml64. exe)](masm-for-x64-ml64-exe.md).

## <a name="syntax"></a>Sözdizimi

> ML \[*seçenekleri*] *dosya adı* \[ \[*Seçenekler*] *filename*]
>
> ML64 \[*Options*] *filename* \[ \[*Seçenekler*] *filename*]... \[/Link *link_options*]

### <a name="parameters"></a>Parametreler

*seçenekler*\
Aşağıdaki tabloda listelenen seçenekler.

|Seçenek|Eylem|
|------------|------------|
|**/AT**|Çok küçük bellek modeli desteğini sunar. . Com biçim dosyaları için gereksinimleri ihlal eden kod yapıları için hata iletileri sunar. Bu seçenek ile eşdeğer değildir [. MODEL](dot-model.md) **küçük** yönergesi.<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/BL** *dosya adı*|Alternatif bir bağlayıcı seçer.|
|**/c**|Yalnızca birleştirir. Bağlama yapmaz.|
|**/COFF**|Nesne modülünün ortak nesne dosyası biçimi (COFF) türünü oluşturur. Win32 derleme dili geliştirmesi için gereklidir.<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/CP**|Tüm kullanıcı tanımlayıcıları durumunu korur.|
|**/Cu**|Tüm tanımlayıcıları büyük harflere eşler (varsayılan).<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/CX**|Ortak ve extern sembollerinde büyük/küçük harf durumunu korur.|
|**/D** *symbol*⟦ =*değer*⟧|Verilen ada sahip bir metin makrosunu tanımlar. *Değer* eksikse, boştur. Boşluklarla ayrılmış birden çok belirteç tırnak işaretleri içine alınmalıdır.|
|**/EP**|Önceden işlenmiş bir kaynak listesini üretir (STDOUT 'a gönderilir). Bkz. **/SF**.|
|**/errorreport** [ **yok** &#124; **Prompt** &#124; **kuyruğu** &#124; **gönderme** ]| Kullanım dışı. Hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir. |
|**/F** *onaltınum*|Yığın boyutunu *onaltısay* bayta ayarlar ( **/Link/Stack**:*Number*ile aynıdır). Değerin onaltılık gösterimde ifade edilmesi gerekir. **/F** ile *onaltısayı*arasında bir boşluk olması gerekir.|
|**/Fe** *dosya adı*|Yürütülebilir dosyayı adlandırır.|
|**/Fl**⟦*filename*⟧|Birleştirilmiş bir kod listesi oluşturur. Bkz. **/SF**.|
|**/FM**⟦*filename*⟧|Bağlayıcı eşleme dosyası oluşturur.|
|**/Fo** *dosya adı*|Bir nesne dosyası adlandırır. Daha fazla bilgi için bkz. [açıklamalar](#remarks).|
|**/FPi**|Kayan nokta aritmetiği (yalnızca karma dil) için öykünücü düzeltmelanları üretir.<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/Fr**⟦*filename*⟧|Bir kaynak Browser. sbr dosyası üretir.|
|**/Fr**⟦*filename*⟧|Kaynak Browser. sbr dosyasının genişletilmiş bir biçimini oluşturur.|
|**/GC**|FORTRAN-or Pascal stili işlev çağırma ve adlandırma kurallarının kullanımını belirtir. **Seçenek diliyle aynı: Pascal**.<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/GD**|C stili işlev çağırma ve adlandırma kuralları kullanımını belirtir. **Seçenek diliyle aynı: C**.<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/GZ**|__Stdcall işlev çağırma ve adlandırma kuralları kullanımını belirtir.  **Seçenek diliyle aynı: STCALL**.<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/H** *numarası*|Dış adları önemli karakter sayısı olarak kısıtlar. Varsayılan değer 31 karakterdir.<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/Help**|ML yardımı için QuickHelp 'i çağırır.|
|**/İ** *yol adı*|İçerme dosyası için yolu ayarlar. En fazla 10 **/ı** seçeneğe izin verilir.|
|**/nologo**|Başarılı derleme için iletileri bastırır.|
|**/OMF**|Nesne modülünün nesne modülü dosya biçimi (OMF) türünü oluşturur.  **/OMF** **/c**gerektirir; ML. exe, OMF nesnelerinin bağlanmasını desteklemez.<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/Sa yazın**|Tüm kullanılabilir bilgilerin listesini etkinleştirir.|
|**/SAFESEH**|Nesneyi herhangi bir özel durum işleyicisi veya ile birlikte gelen özel durum işleyicilerini içeren olarak işaretler [. SAFESEH](dot-safeseh.md).<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/SF**|Listeleme dosyasına ilk geçiş listesi ekler.|
|**/SL** *genişliği*|Kaynak listesinin satır genişliğini satır başına karakter cinsinden ayarlar. Aralık 60, 255 veya 0 ' dır. Varsayılan değer 0 ' dır. [Sayfa](page.md) genişliğiyle aynı.|
|**/Sn**|Bir liste üretilirken sembol tablosunu kapatır.|
|**/SP** *uzunluğu*|Sayfa başına satırlardaki kaynak listesinin sayfa uzunluğunu ayarlar. Aralık 10 ila 255 veya 0 ' dır. Varsayılan değer 0 ' dır. [Sayfa](page.md) uzunluğu ile aynı.|
|**/SS** *metni*|Kaynak listesi için metni belirtir. Alt [başlık](subtitle.md) metniyle aynı.|
|**/St** *metni*|Kaynak listesinin başlığını belirtir. [Başlık](title.md) metniyle aynı.|
|**/SX**|Listede yanlış koşulları etkinleştirir.|
|**/Ta** *dosya adı*|Adı. asm uzantısıyla bitmeyen kaynak dosyayı ayrıştırır.|
|**aralıkları**|**/W0/WX**ile aynı.|
|**/W** *düzeyi*|*Düzey* = 0, 1, 2 veya 3 olan uyarı düzeyini ayarlar.|
|**/WX**|Uyarılar oluşturulduysa bir hata kodu döndürür.|
|**/X**|Ortam yolunu EKLEMEYI yoksay.|
|**/ZD**|Nesne dosyasında satır numarası bilgileri oluşturur.|
|**/ZF**|Tüm sembolleri herkese açık hale getirir.|
|**/Zi**|Nesne dosyasında CodeView bilgileri oluşturur.|
|**/ZM**|Masd 5,1 ile maksimum uyumluluk için**M510** seçeneğini sunar.<br /><br /> Ml64. exe ' de kullanılamaz.|
|**/ZP**⟦*hizalaması*⟧|Belirtilen bayt sınırında yapıları paketler. *Hizalama* 1, 2 veya 4 olabilir.|
|**/ZS**|Yalnızca bir sözdizimi denetimi gerçekleştirir.|
|**/?**|ML komut satırı sözdiziminin özetini görüntüler.|

*dosya adı*\
Dosyanın adı.

*link_options*\
Bağlantı seçenekleri. Daha fazla bilgi için bkz. [bağlayıcı seçenekleri](../../build/reference/linker-options.md).

## <a name="remarks"></a>Açıklamalar

ML ve ML64 için bazı komut satırı seçenekleri yerleştirme duyarlıdır. Örneğin, ML ve ML64 çeşitli **/c** seçeneklerini kabul edebildiğinden, tüm karşılık gelen **/fo** seçeneklerinin **/c**öncesinde belirtilmesi gerekir. Aşağıdaki komut satırı örneği, her derleme dosyası belirtimi için bir nesne dosya belirtimi gösterir:

```cmd
ml.exe /Fo a1.obj /c a.asm /Fo b1.obj /c b.asm
```

## <a name="environment-variables"></a>Ortam Değişkenleri

|Değişken|Açıklama|
|--------------|-----------------|
|INCLUDE|İçerme dosyaları için arama yolunu belirtir.|
|ML|Varsayılan komut satırı seçeneklerini belirtir.|
|KLASÖRÜNE|Geçici dosyalar için yol belirtir.|

## <a name="see-also"></a>Ayrıca bkz.

[Ml hata iletileri](ml-error-messages.md)\
[Microsoft Macro Assembler Başvurusu](microsoft-macro-assembler-reference.md)
