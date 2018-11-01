---
title: /ALLOWBIND
ms.date: 11/04/2016
f1_keywords:
- /allowbind
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
ms.openlocfilehash: 3d38b2a70fc3510b2c26942dc3e5e6fdd76a28e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550533"
---
# <a name="allowbind"></a>/ALLOWBIND

DLL'in bağlı olamayacağını belirtir.

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Açıklamalar

**/ALLOWBIND** seçeneği görüntü bağlanması için izin verildiğini Bind.exe'yi gösteren DLL üst bilgisinde bir bit ayarlar. Yükleyici rebase ve her başvurulan DLL için adres düzeltmesi gerçekleştirmek sahip olmadığında daha hızlı bir şekilde yüklemek bir görüntü bağlama izin verebilirsiniz. Bir DLL dijital olarak imzalanmışsa bağlı olmasını istemeyebilirsiniz — bağlama imzayı geçersiz kılar. Bağlama hiçbir etkisi rastgele adres alanı düzenini (ASLR) kullanarak görüntüyü etkinse **dynamıcbase** ASLR destekleyen Windows sürümleri üzerinde.

Kullanım **/ALLOWBIND:NO** DLL bağlama gelen Bind.exe'yi önlemek için.

Daha fazla bilgi için [/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md) bağlayıcı seçeneği.

## <a name="see-also"></a>Ayrıca Bkz.

[EDITBIN Seçenekleri](../../build/reference/editbin-options.md)