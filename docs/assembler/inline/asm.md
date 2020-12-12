---
description: 'Hakkında daha fazla bilgi edinin: `__asm`'
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
ms.openlocfilehash: 5fa4e64bdb9ae4fc01e6e379de3e8a6771959e80
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118062"
---
# `__asm`

**Microsoft'a Özgü**

**`__asm`** Anahtar sözcüğü satır içi assembler 'yi çağırır ve C veya C++ ifadesinin yasal olduğu her yerde görünebilir. Kendisi tarafından bulunamaz. Ardından, bir derleme yönergesi, küme ayracı içine alınmış bir dizi yönerge veya en azından boş bir küme ayracı olmalıdır. **`__asm`** Burada "Block" terimi, ayraç içinde olsun ya da etmeksizin herhangi bir yönergeyi veya yönerge grubunu ifade eder.

> [!NOTE]
> Standart C++ anahtar sözcüğü için Visual C++ desteği **`asm`** derleyicinin anahtar sözcüğü üzerinde bir hata üretmeyeceği olgusuna sınırlıdır. Ancak, bir **`asm`** blok anlamlı kod oluşturmaz. **`__asm`** Yerine kullanın **`asm`** .

## <a name="grammar"></a>Dilbilgisi

*asm-engelle*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__asm`***bütünleştirilmiş kod-yönerge* **`;`** <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__asm {`***Assembly-instruction-List* **`}`** **`;`** <sub>opt</sub>

*Assembly-instruction-List*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bütünleştirilmiş kod-yönerge* **`;`** <sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*bütünleştirilmiş kod-yönerge* **`;`** *Assembly-instruction-List* **`;`** <sub>opt</sub>

## <a name="remarks"></a>Açıklamalar

Küme ayracı olmadan kullanılırsa, **`__asm`** anahtar sözcüğü satırın geri kalanının derleme dili bir ifade olduğu anlamına gelir. Küme ayraçlarıyla birlikte kullanılırsa, küme ayraçları arasındaki her bir satır bir derleme dili deyimidir. Önceki sürümlerle uyumluluk için, **`_asm`** için bir eş anlamlı **`__asm`** .

**`__asm`** Anahtar sözcüğü bir ekstre ayırıcısı olduğundan, derleme yönergelerini aynı satıra koyabilirsiniz.

Visual Studio 2005 öncesi yönergeleri

```cpp
__asm int 3
```

**/clr** ile derlendiğinde yerel kodun oluşturulmasına neden olmadı; Derleyici, yönergeyi bir CLR kesme yönergesine çevirdi.

`__asm int 3` Artık işlev için yerel kod oluşturmaya neden olur. Bir işlevin kodunuzda bir kesme noktasına neden olmasını istiyorsanız ve bu işlevin MSIL 'e derlendiğini istiyorsanız [__debugbreak](../../intrinsics/debugbreak.md)kullanın.

Önceki sürümlerle uyumluluk için, **`_asm`** **`__asm`** [/za \( Disable dil uzantılarını devre dışı bırak](../../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirlenmediği için bir eş anlamlı.

## <a name="example"></a>Örnek

Aşağıdaki kod parçası, **`__asm`** küme ayraçları içine alınmış basit bir bloğudur:

```cpp
__asm {
   mov al, 2
   mov dx, 0xD007
   out dx, al
}
```

Alternatif olarak, **`__asm`** her derleme yönergesinin önüne koyabilirsiniz:

```cpp
__asm mov al, 2
__asm mov dx, 0xD007
__asm out dx, al
```

**`__asm`** Anahtar sözcüğü bir ifade ayırıcısı olduğundan, aynı satıra derleme yönergeleri de koyabilirsiniz:

```cpp
__asm mov al, 2   __asm mov dx, 0xD007   __asm out dx, al
```

Üç örnek de aynı kodu üretir, ancak ilk stil ( **`__asm`** bloğu küme ayraçları içinde kapsayan) bazı avantajları vardır. Küme ayraçları, derleme kodunu C veya C++ kodundan açıkça ayırır ve anahtar sözcüğünün gereksiz tekrarından kaçınılmasını önler **`__asm`** . Küme ayraçları, belirsizlikleri de engelleyebilir. Bir blok olarak aynı satıra bir C veya C++ ekstresi koymak istiyorsanız **`__asm`** , bloğu küme ayraçları içine almalısınız. Küme ayraçları olmadan derleyici, derleme kodu durdurulduğunda ve C veya C++ deyimlerinin başlayacağı yeri söyleyebilir. Son olarak, küme ayracdaki metin sıradan MASı metniyle aynı biçimde olduğundan, varolan MASı kaynak dosyalarından metin kolayca kesip yapıştırabilirsiniz.

C ve C++ ' daki ayraçların aksine, bir bloğu kapsayan küme ayraçları **`__asm`** değişken kapsamını etkilemez. Ayrıca blokları iç içe geçirebilirsiniz **`__asm`** ; iç içe geçme değişken kapsamını etkilemez.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../../cpp/keywords-cpp.md)<br/>
[Satır içi assembler](../../assembler/inline/inline-assembler.md)<br/>
