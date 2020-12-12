---
description: Daha fazla bilgi edinin:/ıGNORE (belirli uyarıları yoksay)
title: /IGNORE (Belirli Uyarıları Atla)
ms.date: 11/04/2016
f1_keywords:
- /OVERWRITE
helpviewer_keywords:
- /IGNORE linker option
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
ms.openlocfilehash: 7098515a65981ffcdf60b5b517d2434d20e7c015
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191335"
---
# <a name="ignore-ignore-specific-warnings"></a>/IGNORE (Belirli Uyarıları Atla)

```
/IGNORE:warning[,warning]
```

## <a name="parameters"></a>Parametreler

*Warning*<br/>
4000 ile 4999 arasında, bastıryapılacak bağlayıcı uyarısı sayısı.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bağlantı tüm uyarıları raporlar.  `warning` Bağlayıcıya belirli bir uyarı numarasını bastırmasını bildirmek için/Ignore: belirtin. Birden çok uyarıyı yoksaymak için, uyarı numaralarını virgülle ayırın.

Bağlayıcı bazı uyarıların yoksayılmasına izin vermiyor. Bu tabloda **/Ignore** tarafından gizlenen uyarılar listelenmektedir:

| Bağlayıcı uyarısı | İleti |
|--------------------|-|
|LNK4017|`keyword` ifade hedef platformda desteklenmiyor; LIP|
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|' ' seçeneği tanınmadı `option` ; yoksayıldı|
|LNK4062|' ' `option` , ' ' hedef makinesi ile uyumlu değil `architecture` ; seçenek yoksayıldı|
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|"" `option1` belirtime nedeniyle "" yoksayılıyor `option2`|
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|' `function` ' EntryPoint, ' `number` ' bayt bağımsız değişken ile __stdcall değildir; görüntü çalışmayabilir|
|LNK4088|/FORCE seçeneği nedeniyle oluşturulan görüntü; görüntü çalışmayabilir|
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|' ' seçeneği ile hiçbir bağımsız değişken belirtilmedi `option` ; anahtar yoksayılıyor|
|LNK4203|Program veritabanı ' ' okunurken hata `filename` ; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|' `filename` ' öğesine başvuran modül için hata ayıklama bilgileri eksik; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|' `filename` ' öğesine başvuran modül için geçerli hata ayıklama bilgileri eksik; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|önceden derlenmiş tür bilgileri bulunamadı; ' `filename` ' bağlı değil veya üzerine yazıldı; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|LNK4207|' `filename` ' derlenen/Yıc/yu/Z7; pdb oluşturulamıyor;/Zi ile yeniden derleyin; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|LNK4208|' ' içinde uyumsuz PDB biçimi `filename` ; silin ve yeniden oluşturun; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|LNK4209|hata ayıklama bilgileri bozuk; modülü yeniden derleyin; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor|
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option` artık desteklenmiyor; LIP|
|LNK4228|' `option` ' BIR DLL için geçersiz; yoksayıldı|
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|geçersiz yönerge/ `directive` bulunan; yoksayıldı|

Genel olarak, yok sayılacak bağlayıcı uyarıları derleme hatalarını, komut satırı hatalarını veya düzeltilmesi gereken yapılandırma hatalarını temsil eder.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasöründe **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.
