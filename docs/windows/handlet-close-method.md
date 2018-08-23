---
title: HandleT::Close yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ab919b3aeba45462a15900429493225f00909d5a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602460"
---
# <a name="handletclose-method"></a>HandleT::Close Yöntemi

Geçerli kapatır **HandleT** nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
void Close();
```

## <a name="remarks"></a>Açıklamalar

Geçerli altını tanıtıcı **HandleT** kapatılır ve **HandleT** geçersiz duruma ayarlanır.

Tanıtıcı düzgün kapatmadığına, çağıran iş parçacığında bir özel durum oluşturulur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[HandleT Sınıfı](../windows/handlet-class.md)