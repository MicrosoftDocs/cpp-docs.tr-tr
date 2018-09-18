---
title: Komut satırı uyarısı D9041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9041
dev_langs:
- C++
helpviewer_keywords:
- D9041
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70bf82cfdca787898a02fb52926981bfd1a1b3e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033387"
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