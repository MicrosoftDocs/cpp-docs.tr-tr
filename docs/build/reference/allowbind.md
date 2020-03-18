---
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind_bind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 4f5b662223914cbb4970188595afb52cc2500cd4
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440382"
---
# <a name="allowbind"></a>/ALLOWBIND

DLL 'nin bağlanıp bağlanamayacağını belirtir.

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Açıklamalar

**/Allowbind** seçeneği dll 'nin üst bilgisinde, görüntünün bağlı olmasına izin verileceğini belirten bir bit ayarlar. Bağlama, yükleyicinin her bir DLL için yeniden temellendirmeyi ve adres düzeltmesini gerçekleştirmesini gerektirmeyen bir görüntünün daha hızlı yüklenmesine izin verebilir. Dijital olarak imzalanmışsa DLL 'nin bağlanmasını istemeyebilirsiniz; bağlama imzayı geçersiz kılar. Görüntü için adres boşluğu düzeni rastgele seçimi (ASLR), ASLR desteği olan Windows sürümlerinde **/DynamicBase** kullanarak etkin değilse bağlama etkisizdir.

Bind. exe ' nın DLL 'yi bağlamasını engellemek için **/Allowbind: No** komutunu kullanın.

Daha fazla bilgi için [/Allowbind](allowbind-prevent-dll-binding.md) bağlayıcı seçeneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)
