---
description: 'Hakkında daha fazla bilgi edinin: no_smart_pointers Import özniteliği'
title: no_smart_pointers içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_smart_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: cf2299668a2e1b24cdf45069766466f448ee9d66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333274"
---
# <a name="no_smart_pointers-import-attribute"></a>no_smart_pointers içeri aktarma özniteliği

**C++ özel**

Tür kitaplığındaki tüm arabirimler için akıllı işaretçiler oluşturulmasını engeller.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **no_smart_pointers**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, kullandığınızda `#import` , tür kitaplığındaki tüm arabirimler için bir akıllı işaretçi bildirimi alırsınız. Bu akıllı işaretçiler [_com_ptr_t](../cpp/com-ptr-t-class.md)türündedir.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
