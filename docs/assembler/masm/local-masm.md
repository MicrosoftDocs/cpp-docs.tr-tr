---
description: 'Daha fazla bilgi edinin: yerel'
title: LOCAL (MASM)
ms.date: 12/16/2019
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: 27296f69b62de0dcd314b2575f045e06576bbf64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129759"
---
# <a name="local"></a>LOCAL

İlk yönergede, bir makro içinde **Yerel** , makronun her bir örneği için benzersiz olan Etiketler tanımlar.

## <a name="syntax"></a>Syntax

> **Yerel** *LocalId* ⟦, *LocalId* ... ⟧
>
> **Local** *LabelId* ⟦ __\[__ *Count*__]__ ⟧ ⟦__:__*qualifiedtype*⟧ ⟦__,__ *LabelId* ⟦ __\[__ *Count*__]__ ⟧ ⟦*qualifiedtype*⟧... ⟧

## <a name="remarks"></a>Açıklamalar

İkinci yönergede, bir yordam tanımında (**proc**), **Yerel** , yordam süresince var olan yığın tabanlı değişkenler oluşturur. *LabelId* bir basit değişken veya *Count* öğeleri içeren bir dizi olabilir, burada *Count* bir sabit ifadedir.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
