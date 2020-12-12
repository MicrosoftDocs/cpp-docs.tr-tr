---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: bayt dizisine bir Işaretçi alma'
title: 'Nasıl yapılır: Bayt Dizisine Bir İşaretçi Alma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- pointers, to Byte array
- Byte arrays
ms.assetid: aea18073-3341-47f4-9f0e-04e03327037e
ms.openlocfilehash: d76aa9040be5b908edac3a87ae6f0698f6d6a5dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286390"
---
# <a name="how-to-obtain-a-pointer-to-byte-array"></a>Nasıl yapılır: Bayt Dizisine Bir İşaretçi Alma

<xref:System.Byte>İlk öğenin adresini alıp bir işaretçiye atayarak dizideki dizi bloğuna bir işaretçi elde edebilirsiniz.

## <a name="example"></a>Örnek

```cpp
// pointer_to_Byte_array.cpp
// compile with: /clr
using namespace System;
int main() {
   Byte bArr[] = {1, 2, 3};
   Byte* pbArr = &bArr[0];

   array<Byte> ^ bArr2 = gcnew array<Byte>{1,2,3};
   interior_ptr<Byte> pbArr2 = &bArr2[0];
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
