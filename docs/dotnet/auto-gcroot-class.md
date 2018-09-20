---
title: auto_gcroot sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 48412a932ff3752b0613f7045cd88992332b7917
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423240"
---
# <a name="autogcroot-class"></a>auto_gcroot Sınıfı

Otomatik kaynak yönetimi (gibi [auto_ptr sınıfı](../standard-library/auto-ptr-class.md)) yerel bir tür sanal bir işleyici eklemek için kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename _element_type>
class auto_gcroot;
```

#### <a name="parameters"></a>Parametreler

*_element_type*<br/>
Katıştırılmış yönetilen türü.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\auto_gcroot.h >

**Namespace** msclr

## <a name="see-also"></a>Ayrıca Bkz.

[auto_gcroot](../dotnet/auto-gcroot.md)<br/>
[auto_gcroot Members](../dotnet/auto-gcroot-members.md)<br/>
[Nasıl yapılır: Yerel Türlerde İşleyicileri Bildirme](../dotnet/how-to-declare-handles-in-native-types.md)<br/>
[auto_handle Class](../dotnet/auto-handle-class.md)