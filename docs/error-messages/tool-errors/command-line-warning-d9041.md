---
title: Komut Satırı Uyarısı D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: d9a32fbf961e980633635f277a76955a706a4b0e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59021462"
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

## <a name="see-also"></a>Ayrıca bkz.

[Komut Satırı Hataları D8000 - D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC derleyici seçenekleri](../../build/reference/compiler-options.md)