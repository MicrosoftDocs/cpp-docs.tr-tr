---
title: LOCAL (MASM)
ms.date: 08/30/2018
f1_keywords:
- Local
helpviewer_keywords:
- LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
ms.openlocfilehash: c3a04f68b7fd17b2b6459c219a98fd99ec2d62d4
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397248"
---
# <a name="local-masm"></a>LOCAL (MASM)

İlk yönergede, bir makro içinde **Yerel** , makronun her bir örneği için benzersiz olan Etiketler tanımlar.

## <a name="syntax"></a>Sözdizimi

> **Yerel** *LocalName* ⟦, *LocalName* ... ⟧
>
> **Yerel** *etiket* ⟦ __\[__ *Count* __]__ ⟧ ⟦ __:__ *Type*⟧ ⟦ __,__ *etiket* ⟦ __\[__ *Count* __]__ ⟧ ⟦*tür*⟧... ⟧

## <a name="remarks"></a>Açıklamalar

İkinci yönergede, bir yordam tanımında (**proc**), **Yerel** , yordam süresince var olan yığın tabanlı değişkenler oluşturur. *Etiket* basit bir değişken veya *Count* öğeleri içeren bir dizi olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
