---
title: /IGNORE (Belirli Uyarıları Atla)
ms.date: 11/04/2016
f1_keywords:
- /OVERWRITE
helpviewer_keywords:
- /IGNORE linker option
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
ms.openlocfilehash: 2b374e0e73f9fc14fa32ea4f63fa71039a5cf3c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270161"
---
# <a name="ignore-ignore-specific-warnings"></a>/IGNORE (Belirli Uyarıları Atla)

```
/IGNORE:warning[,warning]
```

## <a name="parameters"></a>Parametreler

*warning*<br/>
Bağlayıcı, aralığında 4000 için 4999 gizlemek için uyarı sayısı.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tüm uyarılar bağlantısı bildirir. Belirtin **yoksay:** `warning` belirli bir uyarı numarası bastırmak için bağlayıcı söylemek için. Birden çok uyarılarını gözardı etme uyarı numaralarını virgülle ayırın.

Bağlayıcı, bazı uyarılar yok sayılacak izin vermez. Bu tabloda tarafından gizlenen olmayan uyarıların **Yoksay**:

|Bağlayıcı Uyarısı||
|--------------------|-|
|LNK4017|`keyword` deyimi; için hedef platform desteklenmiyor yoksayıldı|
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|Tanınmayan seçenek '`option`'; yoksayıldı|
|LNK4062|'`option`'ile uyumlu değil'`architecture`' hedef makine; seçenek yoksayıldı|
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|yoksayma "`option1`"için"`option2`" belirtimi|
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|Giriş Noktası '`function`'ile __stdcall değildir'`number`' bayt bağımsız değişken; görüntü çalışmayabilir|
|LNK4088|/ Force seçeneği nedeniyle oluşturulan görüntü; Görüntü çalışmayabilir|
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|seçeneği ile belirtilen hiçbir bağımsız değişken '`option`'; göz ardı anahtarı|
|LNK4203|Program veritabanı okunurken hata oluştu '`filename`'; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|'`filename`' modülü; başvuru için hata ayıklama eksik nesne hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|'`filename`' başvuru modülü; için geçerli hata ayıklama bilgileri eksik nesne hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|önceden derlenmiş tür bilgileri bulunamadı; '`filename`' değil bağlantılı veya üzerine yazılmış; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|LNK4207|'`filename`' /Yc /Yu/z7 derledi; PDB; /Zi ile yeniden derleyin; bağlama nesnesi yok hata ayıklama bilgileri yokmuş gibi oluşturulamıyor|
|LNK4208|içinde uyumsuz PDB formatı '`filename`'; silin ve yeniden derleyin; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|LNK4209|hata ayıklama bilgileri bozuk; Modülü yeniden derleyin; Nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option` artık desteklenmiyor; yoksayıldı|
|LNK4228|'`option`' DLL için geçersiz; yoksayıldı|
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|Geçersiz yönerge /`directive` bulundu; yoksayıldı|

Genel olarak, göz ardı edilemez bağlayıcı uyarılarını derleme hatalarını, komut satırı hataları veya düzelmeniz gerekmektedir yapılandırma hataları temsil eder.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. İçinde **bağlayıcı** klasörüne **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.