---
title: Komut Satırı Uyarısı D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: 7c685a1ca3195ad4ab52bab8b5d32b1a51534b24
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196581"
---
# <a name="command-line-warning-d9041"></a>Komut Satırı Uyarısı D9041

'/Option ' için geçersiz değer ' Value '; ' Value ' varsayılıyor; Bu uyarıyı belirtirken komut satırı seçeneklerine '/Analyze ' ekleyin

**/WD**, **/we**, **/Wo**veya **/WL** komut satırı seçeneğine de **/Analyze** komut satırı seçeneği belirtilmeden bir kod analizi uyarı numarası eklendi. Bu hatayı çözmek için, **/Analyze** komut satırı seçeneğini ekleyin veya uygun **/w** komut satırı seçeneğinden geçersiz uyarı numarasını kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki komut satırı örneği, D9041 uyarısını üretir:

```
cl /EHsc /LD /wd6001 filename.cpp
```

Uyarıyı onarmak için **/Analyze** komut satırı seçeneğini ekleyin. Derleyici sürümünüzde **/Analyze** desteklenmiyorsa, **/WD** seçeneğinden geçersiz uyarı numarasını kaldırın.

## <a name="see-also"></a>Ayrıca bkz.

[D8000 ile D9999 Arasındaki Komut Satırı Hataları](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC Derleyicisi Seçenekleri](../../build/reference/compiler-options.md)
