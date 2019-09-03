---
title: no_smart_pointers içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_smart_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: 1fca3eb486ff3cfc7403c38e91855b799a698782
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220693"
---
# <a name="no_smart_pointers-import-attribute"></a>no_smart_pointers içeri aktarma özniteliği

**C++Belirli**

Tür kitaplığındaki tüm arabirimler için akıllı işaretçiler oluşturulmasını engeller.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **no_smart_pointers**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, kullandığınızda `#import`, tür kitaplığındaki tüm arabirimler için bir akıllı işaretçi bildirimi alırsınız. Bu akıllı işaretçiler [_com_ptr_t](../cpp/com-ptr-t-class.md)türüdür.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
