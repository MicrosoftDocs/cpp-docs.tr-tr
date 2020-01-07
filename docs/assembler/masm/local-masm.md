---
title: LOCAL (MASM)
ms.date: 12/16/2019
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 2bef6b26f1b922be6512bd6ebe8e0b2627e86f45
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317155"
---
# <a name="local"></a>LOCAL

İlk yönergede, bir makro içinde **Yerel** , makronun her bir örneği için benzersiz olan Etiketler tanımlar.

## <a name="syntax"></a>Sözdizimi

> **Yerel** *LocalId* ⟦, *LocalId* ... ⟧
>
> **Yerel** *LabelId* ⟦ __\[__ *Count* __]__ ⟧ ⟦ __:__ *qualifiedtype*⟧ ⟦ __,__ *LabelId* ⟦ __\[__ *Count* __]__ ⟧ ⟦*qualifiedtype*⟧... ⟧

## <a name="remarks"></a>Açıklamalar

İkinci yönergede, bir yordam tanımında (**proc**), **Yerel** , yordam süresince var olan yığın tabanlı değişkenler oluşturur. *LabelId* bir basit değişken veya *Count* öğeleri içeren bir dizi olabilir, burada *Count* bir sabit ifadedir.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
