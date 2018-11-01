---
title: Komut Satırı Uyarısı D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: 79bdafcd4ed6af061b9c0ee27aae6eed6bc981a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513925"
---
# <a name="command-line-warning-d9041"></a>Komut Satırı Uyarısı D9041

geçersiz değer 'value' için '/ seçenek'; ' değeri '; Ekle ' / analyze' Bu uyarıyı belirtirken komut satırı seçenekleri

Kod Analizi uyarı numarası için eklenen **/wd**, **/we**, **/wo**, veya **/wl** dabelirtilmedenkomutsatırıseçeneği **/ analyze** komut satırı seçeneği. Bu hatayı düzeltmek için ya da ekleme **/ analyze** komut satırı seçeneği veya geçersiz bir uyarı numarası uygun kaldırmak **/w** komut satırı seçeneği.

## <a name="example"></a>Örnek

Aşağıdaki örnek komut satırı uyarısı D9041 oluşturur:

```
cl /EHsc /LD /wd6001 filename.cpp
```

Uyarıyı çözmek için ekleme **/ analyze** komut satırı seçeneği. Varsa **/ analyze** olduğundan derleyici sürümünüze desteklenmiyor, Kaldır geçersiz uyarı numarasını **/wd** seçeneği.

## <a name="see-also"></a>Ayrıca Bkz.

[D8000 ile D9999 Arasındaki Komut Satırı Hataları](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)