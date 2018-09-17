---
title: -INTEGRITYCHECK (imza denetimi iste) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31df513a40b60fcb57c48f0d20e124fc77888d99
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703136"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (İmza Denetimi İste)

İkili görüntünün dijital imzasının yükleme sırasında denetlenmesi gerektiğini belirtir.

```
/INTEGRITYCHECK[:NO]
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **/INTEGRITYCHECK** kapalıdır.

**/INTEGRITYCHECK** seçenek kümeleri — DLL dosyasının veya yürütülebilir dosyanın PE üstbilgisine — Windows görüntüyü yüklemek için dijital imza için denetlenecek bellek yöneticisi için bir bayrak. Bu seçenek, bazı Windows özellikleri tarafından yüklenen çekirdek modu kodunu uygulayan hem 32-bit hem de 64-bit DLL'ler için ayarlanması gerekir ve Windows Vista, Windows 7, Windows 8, Windows Server 2008 ve Windows Server 2012 üzerindeki tüm aygıt sürücüleri için tavsiye edilir. Windows Vista'dan önceki Windows sürümlerinde bu bayrağı yoksayın. Daha fazla bilgi için [zorla bütünlük imzalama taşınabilir yürütülebilir (PE) dosyaları](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneğini ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler**, girin `/INTEGRITYCHECK` veya `/INTEGRITYCHECK:NO`.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
[Bütünlük imzalama taşınabilir yürütülebilir (PE) dosyaların zorla](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)
[çekirdek modu kod imzalama anlatımı](https://msdn.microsoft.com/windows/hardware/gg487328.aspx)<br/>
[Windows 7 ve Windows Server 2008'de Appınit DLL'leri](https://msdn.microsoft.com/windows/hardware/gg463040.aspx)