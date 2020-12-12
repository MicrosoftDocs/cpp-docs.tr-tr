---
description: Daha fazla bilgi edinin:/ALLOWBIND
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind_bind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 54f3056240537d765a9212e774a9a313ded49dab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179609"
---
# <a name="allowbind"></a>/ALLOWBIND

DLL 'nin bağlanıp bağlanamayacağını belirtir.

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Açıklamalar

**/Allowbind** seçeneği, bir dll üst bilgisinde görüntünün bağlı olmasına izin verildiğini Bind.exe belirten bir bit ayarlar. Bağlama, yükleyicinin her bir DLL için yeniden temellendirmeyi ve adres düzeltmesini gerçekleştirmesini gerektirmeyen bir görüntünün daha hızlı yüklenmesine izin verebilir. Dijital olarak imzalanmışsa DLL 'nin bağlanmasını istemeyebilirsiniz; bağlama imzayı geçersiz kılar. Görüntü için adres boşluğu düzeni rastgele seçimi (ASLR), ASLR desteği olan Windows sürümlerinde **/DynamicBase** kullanarak etkin değilse bağlama etkisizdir.

Bind.exe DLL 'nin bağlamasını engellemek için **/Allowbind: No** kullanın.

Daha fazla bilgi için [/Allowbind](allowbind-prevent-dll-binding.md) bağlayıcı seçeneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)
