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
ms.openlocfilehash: 4cb7e5a3627d865e2f2193dee096c72cced75f5f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273202"
---
# <a name="allowbind"></a>/ALLOWBIND

DLL'in bağlı olamayacağını belirtir.

```

/ALLOWBIND[:NO]
```

## <a name="remarks"></a>Açıklamalar

**/ALLOWBIND** seçeneği görüntü bağlanması için izin verildiğini Bind.exe'yi gösteren DLL üst bilgisinde bir bit ayarlar. Yükleyici rebase ve her başvurulan DLL için adres düzeltmesi gerçekleştirmek sahip olmadığında daha hızlı bir şekilde yüklemek bir görüntü bağlama izin verebilirsiniz. Bir DLL dijital olarak imzalanmışsa bağlı olmasını istemeyebilirsiniz — bağlama imzayı geçersiz kılar. Bağlama hiçbir etkisi rastgele adres alanı düzenini (ASLR) kullanarak görüntüyü etkinse **dynamıcbase** ASLR destekleyen Windows sürümleri üzerinde.

Kullanım **/ALLOWBIND:NO** DLL bağlama gelen Bind.exe'yi önlemek için.

Daha fazla bilgi için [/ALLOWBIND](allowbind-prevent-dll-binding.md) bağlayıcı seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)
