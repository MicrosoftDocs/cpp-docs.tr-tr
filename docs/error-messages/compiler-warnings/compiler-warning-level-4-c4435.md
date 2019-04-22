---
title: Derleyici Uyarısı (düzey 4) C4435
ms.date: 11/04/2016
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
ms.openlocfilehash: 43c13c484d6e9accee7c4d2c58b72a4539a75c4c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041234"
---
# <a name="compiler-warning-level-4-c4435"></a>Derleyici Uyarısı (düzey 4) C4435

'class1': / Vd2 altındaki Nesne düzeni 'class2' sanal tabanı nedeniyle değiştirir

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

/ Vd1 seçeneği altında varsayılan derliyorsanız, türetilmiş sınıf olmayan bir `vtordisp` için belirtilen sanal temel alan.  Varsa/vd2 veya `#pragma vtordisp(2)` kıyaslandığında geçerli bir `vtordisp` alan nesne düzeni değiştirme mevcut olacaktır.  Etkileşim kuran modülleri ile farklı derlenir, bu ikili uyumluluğu sorunlarına yol açabilecek `vtordisp` ayarları.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4435 oluşturur.

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