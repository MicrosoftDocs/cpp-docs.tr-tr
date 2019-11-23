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

In the first directive, within a macro, **LOCAL** defines labels that are unique to each instance of the macro.

## <a name="syntax"></a>Sözdizimi

> **LOCAL** *localname* ⟦, *localname* ...⟧
>
> **LOCAL** *label* ⟦ __\[__ *count* __]__ ⟧ ⟦ __:__ *type*⟧ ⟦ __,__ *label* ⟦ __\[__ *count* __]__ ⟧ ⟦*type*⟧ ...⟧

## <a name="remarks"></a>Açıklamalar

In the second directive, within a procedure definition (**PROC**), **LOCAL** creates stack-based variables that exist for the duration of the procedure. The *label* may be a simple variable or an array containing *count* elements.

## <a name="see-also"></a>Ayrıca bkz.

[Directives reference](directives-reference.md)
