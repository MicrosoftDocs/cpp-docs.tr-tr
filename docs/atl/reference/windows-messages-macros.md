---
description: 'Hakkında daha fazla bilgi edinin: Windows Iletileri makroları'
title: Windows Iletileri makroları
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
ms.openlocfilehash: be5913c5eaa88ca0020a978f2b3f6686a6756715
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157587"
---
# <a name="windows-messages-macros"></a>Windows Iletileri makroları

Bu makro pencere iletilerini iletir.

|Ad|Açıklama|
|-|-|
|[WM_FORWARDMSG](#wm_forwardmsg)|Bir pencere tarafından alınan bir iletiyi işlenmek üzere başka bir pencereye iletmek için kullanın.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="wm_forwardmsg"></a><a name="wm_forwardmsg"></a> WM_FORWARDMSG

Bu makro, bir pencere tarafından alınan bir iletiyi işlenmek üzere başka bir pencereye iletir.

```
WM_FORWARDMSG
```

### <a name="return-value"></a>Dönüş Değeri

İleti işlendiyse sıfır dışında, değilse sıfır.

### <a name="remarks"></a>Açıklamalar

Bir pencere tarafından alınan bir iletiyi işlenmek üzere başka bir pencereye iletmek için WM_FORWARDMSG kullanın. LPARAM ve WPARAM parametreleri aşağıdaki gibi kullanılır:

|Parametre|Kullanım|
|---------------|-----------|
|WPARAM|Kullanıcı tarafından tanımlanan veriler|
|LPARAM|`MSG`İleti hakkında bilgi içeren bir yapıya yönelik işaretçi|

### <a name="example"></a>Örnek

Aşağıdaki örnekte, `m_hWndOther` Bu iletiyi alan diğer pencereyi temsil eder.

[!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
