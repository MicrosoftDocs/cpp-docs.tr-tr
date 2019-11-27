---
title: .PUSHFRAME
ms.date: 08/30/2018
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: b0f047278f6250d5ef359f7992df4ea23f4bbd9b
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398042"
---
# <a name="pushframe"></a>.PUSHFRAME

Bir `UWOP_PUSH_MACHFRAME` bırakma kodu girişi oluşturur. İsteğe bağlı *kod* belirtilmişse, geriye doğru izleme kod girişine 1 değiştiricisi verilir. Aksi takdirde değiştirici 0 ' dır.

## <a name="syntax"></a>Sözdizimi

> **. PUSHFRAME** ⟦*kodu*⟧;;

## <a name="remarks"></a>Açıklamalar

. PUSHFRAME, ml64. exe kullanıcılarına, bir çerçeve işlevinin yük dışı bırakma ve [işlem çerçevesi bildiriminden](../../assembler/masm/proc.md) öğesine genişleyen yalnızca prolog içinde nasıl izin verileceğini belirlemesine izin verir [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) yönergesi. Bu yönergeler kod oluşturmaz; yalnızca `.xdata` ve `.pdata`oluşturur. **. PUSHFRAME** , önünde olmayan eylemleri gerçekten uygulayan yönergelerden önce gelmelidir. Anlaşma sağlamak için hem bırakma yönergelerini hem de bir makroya geri doğru bir şekilde kaydırmak için iyi bir uygulamadır.

Daha fazla bilgi için bkz. [for x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
