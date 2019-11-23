---
title: ALIGN (MASM)
ms.date: 01/02/2019
f1_keywords:
- align
helpviewer_keywords:
- ALIGN directive
ms.assetid: 1c386b23-439f-4ec3-a6de-74427b25e47f
ms.openlocfilehash: 22b18f2e238c780377b84fc2be3eb6678686bb73
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74399282"
---
# <a name="align-masm"></a>ALIGN (MASM)

The **ALIGN** directive aligns the next data element or instruction on an address that is a multiple of its parameter. The parameter must be a power of 2 (for example, 1, 2, 4, and so on) that is less than or equal to the segment alignment.

## <a name="syntax"></a>Sözdizimi

> **ALIGN** ⟦*number*⟧

## <a name="remarks"></a>Açıklamalar

The **ALIGN** directive allows you to specify the beginning offset of a data element or an instruction. Aligned data can improve performance, at the expense of wasted space between data elements. Large performance improvements can be seen when data accesses are on boundaries that fit within cache lines. Accesses on natural boundaries for native types means less time spent in internal hardware realignment microcode.

The need for aligned instructions is rare on modern processors that use a flat addressing model, but may be required for jump targets in older code for other addressing models.

When data is aligned, the skipped space is padded with zeroes. When instructions are aligned, the skipped space is filled with appropriately-sized NOP instructions.

## <a name="see-also"></a>Ayrıca bkz.

[EVEN](even.md)\
[Directives reference](directives-reference.md)
