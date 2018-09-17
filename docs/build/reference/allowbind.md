---
title: -ALLOWBIND | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ce0a33ebb0b8b9ba34ac241c8335e9524dec08b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715580"
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