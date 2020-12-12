---
description: 'Hakkında daha fazla bilgi edinin: Command-Line Warning D9041'
title: Komut Satırı Uyarısı D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: d6226d4e5dd89176c0ed3722a9fd24e1244cacac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119768"
---
# <a name="command-line-warning-d9041"></a>Komut Satırı Uyarısı D9041

> '/*Option-Name*' için geçersiz değer '*Option-Value*'; '*varsayıldı-Value*' varsayılıyor Bu uyarıyı belirtirken komut satırı seçeneklerine '/Analyze ' ekleyin

**`/wd`** **`/we`** **`/wo`** **`/wl`** Komut satırı seçeneği belirtilmeden,,, veya komut satırı seçeneğine **`/analyze`** bir kod analizi uyarı numarası eklendi. Bu hatayı çözmek için, **`/analyze`** komut satırı seçeneğini ekleyin veya uygun komut satırı seçeneğinden geçersiz uyarı numarasını kaldırın **`/w`** .

## <a name="example"></a>Örnek

Aşağıdaki komut satırı örneği, D9041 uyarısını üretir:

```cmd
cl /EHsc /LD /wd6001 filename.cpp
```

Uyarıyı onarmak için **`/analyze`** komut satırı seçeneğini ekleyin. **`/analyze`** Derleyicinin sürümünde desteklenmiyorsa, seçenekten geçersiz uyarı numarasını kaldırın **`/wd`** .

## <a name="see-also"></a>Ayrıca bkz.

[D8000 ile D9999 Arasındaki Komut Satırı Hataları](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC derleyici seçenekleri](../../build/reference/compiler-options.md)
