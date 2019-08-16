---
title: /INTEGRITYCHECK (İmza Denetimi İste)
ms.date: 11/04/2016
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
ms.openlocfilehash: 1732c612501b66753635b272f94764975c555f75
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492840"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (İmza Denetimi İste)

İkili görüntünün dijital imzasının yükleme zamanında denetlenmesi gerektiğini belirtir.

```
/INTEGRITYCHECK[:NO]
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **/IntegrityCheck** kapalıdır.

DLL dosyasının veya yürütülebilir dosyanın PE üstbilgisindeki **/IntegrityCheck** seçenek kümeleri — Windows 'da yansımanın yüklenmesi için bellek yöneticisinin dijital imzayı denetlemesi için bir bayrak. Bu seçenek, bazı Windows özellikleri tarafından yüklenen çekirdek modu kodunu uygulayan 32-bit ve 64-bit DLL 'Ler için ayarlanmalıdır ve Windows Vista, Windows 7, Windows 8, Windows Server 2008 ve Windows Server 2012 üzerindeki tüm cihaz sürücüleri için önerilir. Windows Vista 'dan önceki Windows sürümleri bu bayrağı yoksayar. Daha fazla bilgi için bkz. [taşınabilir yürütülebilir (PE) dosyaları Için zorlanan bütünlük imzalama](https://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünü genişletin.

1. **Bağlayıcı** düğümünü genişletin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler**' de, `/INTEGRITYCHECK` veya `/INTEGRITYCHECK:NO`girin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)<br/>
[Taşınabilir yürütülebilir (PE) dosyaları için zorlanan bütünlük Imzalama](https://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)<br/>
[Çekirdek modu kod Imzalama gereksinimleri](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-)<br/>
[AppInit dll 'Leri ve güvenli önyükleme](/windows/win32/dlls/secure-boot-and-appinit-dlls)
