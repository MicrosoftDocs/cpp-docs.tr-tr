---
title: __asm
ms.date: 10/09/2018
f1_keywords:
- __asm
- _asm
- __asm_cpp
helpviewer_keywords:
- __asm keyword [C++], vs. asm blocks
- __asm keyword [C++]
ms.assetid: 77ff3bc9-a492-4b5e-85e1-fa4e414e79cd
ms.openlocfilehash: de28e4c0fad6b89a62b4479c5c32f0b8606cf3af
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169637"
---
# <a name="__asm"></a>__asm

**Microsoft 'a özgü**

`__asm` anahtar sözcüğü satır içi assembler çağırır ve bir C ya da C++ deyimin yasal olduğu her yerde görünebilir. Kendisi tarafından bulunamaz. Ardından, bir derleme yönergesi, küme ayracı içine alınmış bir dizi yönerge veya en azından boş bir küme ayracı olmalıdır. Burada "`__asm` Block" terimi, ayraç içinde olsun veya etmeksizin herhangi bir yönergeyi veya yönerge grubunu ifade eder.

> [!NOTE]
> Standart C++ C++ `asm` anahtar sözcüğü için görsel destek, derleyicinin anahtar sözcüğü üzerinde bir hata üretmeyeceği olgusuna sınırlıdır. Ancak, `asm` bloğu anlamlı bir kod oluşturmaz. `asm`yerine `__asm` kullanın.

## <a name="grammar"></a>Dilbilgisi

*asm-engelle*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__asm** *derleme-yönerge* **;** <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__asm {** *Assembly-instruction-List* **}** **;** <sub>opt</sub>

*Assembly-instruction-List*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*derlemesi-yönerge* **;** <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Assembly-yönerge* **;** *Assembly-instruction-List* **;** <sub>opt</sub>

## <a name="remarks"></a>Açıklamalar

Küme ayracı olmadan kullanılırsa, `__asm` anahtar sözcüğü, satırın geri kalanının derleme dili bir ifade olduğu anlamına gelir. Küme ayraçlarıyla birlikte kullanılırsa, küme ayraçları arasındaki her bir satır bir derleme dili deyimidir. Önceki sürümlerle uyumluluk için, `_asm` `__asm`eşanlamlısıdır.

`__asm` anahtar sözcüğü bir ifade ayırıcısı olduğundan, derleme yönergelerini aynı satıra koyabilirsiniz.

Visual Studio 2005 öncesi yönergeleri

```cpp
__asm int 3
```

**/clr**ile derlendiğinde yerel kodun oluşturulmasına neden olmadı; Derleyici, yönergeyi bir CLR kesme yönergesine çevirdi.

`__asm int 3` artık işlev için yerel kod oluşturmaya neden olur. Bir işlevin kodunuzda bir kesme noktasına neden olmasını istiyorsanız ve bu işlevin MSIL 'e derlendiğini istiyorsanız [__debugbreak](../../intrinsics/debugbreak.md)kullanın.

Önceki sürümlerle uyumluluk için, [/za \(dil uzantılarını devre dışı bırak](../../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde, **_asm** **__asm** için bir eş anlamlı.

## <a name="example"></a>Örnek

Aşağıdaki kod parçası, küme ayraçları içine alınmış basit bir `__asm` bloğudur:

```cpp
__asm {
   mov al, 2
   mov dx, 0xD007
   out dx, al
}
```

Alternatif olarak, her derleme yönergesinin önüne `__asm` koyabilirsiniz:

```cpp
__asm mov al, 2
__asm mov dx, 0xD007
__asm out dx, al
```

`__asm` anahtar sözcüğü bir ifade ayırıcısı olduğundan, aynı satıra derleme yönergeleri de koyabilirsiniz:

```cpp
__asm mov al, 2   __asm mov dx, 0xD007   __asm out dx, al
```

Üç örnek de aynı kodu oluşturur, ancak ilk stil (`__asm` bloğunu ayraç içine alarak) bazı avantajları vardır. Küme ayraçları, derleme kodunu C veya C++ koddan açıkça ayırır ve `__asm` anahtar sözcüğünün gereksiz tekrarından kaçınılmasını önler. Küme ayraçları, belirsizlikleri de engelleyebilir. Bir C veya C++ ifadesini `__asm` bloğu ile aynı satıra koymak istiyorsanız, bloğu küme ayraçları içine almalısınız. Küme ayraçları olmadan derleyici, derleme kodunun durdurduğunu ve C veya C++ deyimleri başlamasını söylemez. Son olarak, küme ayracdaki metin sıradan MASı metniyle aynı biçimde olduğundan, varolan MASı kaynak dosyalarından metin kolayca kesip yapıştırabilirsiniz.

C ve C++içindeki ayraçların aksine, bir `__asm` bloğunu kapsayan küme ayraçları değişken kapsamını etkilemez. Ayrıca, `__asm` blokları iç içe geçirebilirsiniz; iç içe geçme değişken kapsamını etkilemez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../../cpp/keywords-cpp.md)<br/>
[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
