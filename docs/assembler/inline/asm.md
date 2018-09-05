---
title: __asm | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- __asm
- __asm_cpp
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], vs. asm blocks
- __asm keyword [C++]
ms.assetid: 77ff3bc9-a492-4b5e-85e1-fa4e414e79cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bfe0cac0a35c821f3275ec323181f04c1ab982c4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693009"
---
# <a name="asm"></a>__asm

**Microsoft'a özgü**

`__asm` Anahtar sözcüğü satır içi assembler çağırır ve her yerde bir C veya C++ deyiminin geçerli olduğu durumda görünebilir. Kendisi tarafından bulunamaz. Derleme yönergesinde, köşeli ayraçlar veya en azından içine yönergeler grubu tarafından gelmelidir bir çift boş tırnak işaretinin izlemesi. Terim "`__asm` blok" burada herhangi bir yönerge ya da küme ayraçları içinde olsun veya olmasın yönergeler grubu anlamına gelir.

> [!NOTE]
> Visual C++ desteği için standart C++ `asm` anahtar sözcüğü, derleyicinin anahtar sözcükle bir hata oluşturmaz olgu sınırlıdır. Ancak, bir `asm` blok herhangi bir anlamlı kod üretmez. Kullanım `__asm` yerine `asm`.

## <a name="grammar"></a>Dilbilgisi

*asm bloğu*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__asm** *derleme yönergesinin* **;** <sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__asm {** *derleme yönerge listesi* **}** **;** <sub>iyileştirilmiş</sub>

*derleme yönerge listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*derleme yönergesinin* **;** <sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*derleme yönergesinin* **;** *derleme yönerge listesi* **;** <sub>iyileştirilmiş</sub>

## <a name="remarks"></a>Açıklamalar

Küme ayraçları olmadan kullanılırsa `__asm` anahtar sözcüğü, satırın geri kalanını bir çevirici dil ifadesi olduğu anlamına gelir. Ayraçlarıyla kullanıldıysa, küme ayraçları arasındaki her satır bir çevirici dil ifadesi olduğu anlamına gelir. Önceki sürümlerle uyumluluk için `_asm` eşanlamlıdır `__asm`.

Bu yana `__asm` anahtar sözcüğü bir deyim ayırıcısı olduğundan, derleme yönergelerini aynı satıra koyabilirsiniz.

Visual C++ 2005'ten önce yönerge

```cpp
__asm int 3
```

Yerel kod ile derlendiğinde oluşturulmasına neden olmadı **/CLR**; derleyici yönergeyi bir CLR kesme yönergesine çevrilir.

`__asm int 3` artık işlev için yerel kod oluşturmayla sonuçlanır. Bir işlevin kodunuzda bir kesme noktası neden ve bu işlevin MSIL olarak derlenmiş istiyorsanız kullanmak istiyorsanız [__debugbreak](../../intrinsics/debugbreak.md).

## <a name="example"></a>Örnek

Aşağıdaki kod parçası, basit bir `__asm` blok küme ayraçları içine alınmış:

```cpp
__asm {
   mov al, 2
   mov dx, 0xD007
   out dx, al
}
```

Alternatif olarak, koyabilirsiniz `__asm` her bir derleme yönergesinin önüne:

```cpp
__asm mov al, 2
__asm mov dx, 0xD007
__asm out dx, al
```

Çünkü `__asm` anahtar sözcüğü bir deyim ayırıcısı olduğundan, derleme yönergelerini aynı satıra koyabilirsiniz:

```cpp
__asm mov al, 2   __asm mov dx, 0xD007   __asm out dx, al
```

Üç örneğin hepsi aynı kodu, ancak ilk stil oluşturma (kapsayan `__asm` bloğunu ayraç içinde) bazı avantajlar içerir. Küme ayraçları açıkça derleme kodu C veya C++ kodundan ayırın ve tekrarından kaçınır `__asm` anahtar sözcüğü. Küme ayraçları ayrıca belirsizlikleri de engeller. Aynı satıra bir C veya C++ ifadesi koymak istiyorsanız bir `__asm` bloğu, bloğun tırnak içine almalısınız. Parantezler olmadan derleyici, derleme kodunun durduğu ve C veya C++ deyimlerinin nerede başlaması bildiremez. Son olarak, ayraç içindeki metin normal MASM metniyle aynı biçimde olduğundan, kolayca kesebilir ve metni mevcut MASM kaynak dosyalarından yapıştırın.

C ve C++, çevreleyen parantezler içindeki küme ayraçlarından farklı olarak bir `__asm` blok değişken kapsamını etkilemez. Ayrıca yuvalayabilirsiniz `__asm` blokları; değişken kapsamını etkilemez.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../../cpp/keywords-cpp.md)<br/>
[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>