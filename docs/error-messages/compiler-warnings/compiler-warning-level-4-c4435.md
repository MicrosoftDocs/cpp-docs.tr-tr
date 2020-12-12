---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4435'
title: Derleyici Uyarısı (düzey 4) C4435
ms.date: 11/04/2016
f1_keywords:
- C4435
helpviewer_keywords:
- C4435
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
ms.openlocfilehash: ce5ee4e32f6efa1e7986d55fafa0ceec8b754351
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203516"
---
# <a name="compiler-warning-level-4-c4435"></a>Derleyici Uyarısı (düzey 4) C4435

'class1' : /vd2 altındaki nesne düzeni 'class2' sanal tabanı nedeniyle değişecek

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

/Vd1 öğesinin varsayılan derleme seçeneğinin altında, türetilmiş sınıfın `vtordisp` belirtilen sanal taban için bir alanı yoktur.  /VD2 veya etkinse `#pragma vtordisp(2)` , `vtordisp` nesne düzeni değiştirilerek bir alan mevcut olacaktır.  Bu, etkileşimli modüller farklı ayarlarla derlenirse ikili uyumluluk sorunlarına yol açabilir `vtordisp` .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4435 oluşturur.

```cpp
// C4435.cpp
// compile with: /c /W4
#pragma warning(default : 4435)
class A
{
public:
    virtual ~A() {}
};

class B : public virtual A  // C4435
{};
```

## <a name="see-also"></a>Ayrıca bkz.

[vtordisp](../../preprocessor/vtordisp.md)<br/>
[/vd (oluşturma yerini çıkar)](../../build/reference/vd-disable-construction-displacements.md)
