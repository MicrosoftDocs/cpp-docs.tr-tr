---
title: Komut Satırı Uyarısı D9041
ms.date: 11/04/2016
f1_keywords:
- D9041
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
ms.openlocfilehash: d9a32fbf961e980633635f277a76955a706a4b0e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62213789"
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

[D8000 ile D9999 Arasındaki Komut Satırı Hataları](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)<br/>
[MSVC Derleyicisi Seçenekleri](../../build/reference/compiler-options.md)