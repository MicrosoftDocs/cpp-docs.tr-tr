---
title: Event::operator = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c95ac2e16ef4f4b279f0da287a4ca2a3d0f18a7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610469"
---
# <a name="eventoperator-operator"></a>Event::operator= İşleci

Belirtilen atar **olay** geçerli başvuru **olay** örneği.

## <a name="syntax"></a>Sözdizimi

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parametreler

*h*  
Bir rvalue başvurusuna bir **olay** örneği.

## <a name="return-value"></a>Dönüş Değeri

Geçerli bir işaretçi **olay** örneği.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Olay Sınıfı (Windows Çalışma Zamanı C++ Şablon Kitaplığı)](../windows/event-class-windows-runtime-cpp-template-library.md)