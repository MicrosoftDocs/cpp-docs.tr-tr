---
title: Derleyici Uyarısı (düzey 4) C4435
ms.date: 11/04/2016
f1_keywords:
- C4435
helpviewer_keywords:
- C4435
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
ms.openlocfilehash: 0ff545d3de3ef173cdbfd99d7714890e8631ce7a
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810667"
---
# <a name="compiler-warning-level-4-c4435"></a>Derleyici Uyarısı (düzey 4) C4435

'class1' : /vd2 altındaki nesne düzeni 'class2' sanal tabanı nedeniyle değişecek

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

/Vd1 öğesinin varsayılan derleme seçeneğinin altında, türetilmiş sınıfın belirtilen sanal taban için `vtordisp` alanı yoktur.  /VD2 veya `#pragma vtordisp(2)` etkinse, nesne düzeni değiştirilerek bir `vtordisp` alanı mevcut olacaktır.  Bu, etkileşim modülleri farklı `vtordisp` ayarlarıyla derlenirse ikili uyumluluk sorunlarına yol açabilir.

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
[/vd (Yapı Yer Değiştirmelerini Devre Dışı Bırak)](../../build/reference/vd-disable-construction-displacements.md)