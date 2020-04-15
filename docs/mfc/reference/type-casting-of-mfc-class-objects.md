---
title: MFC Sınıf Nesnelerine İlişkin Tür Atama
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
ms.openlocfilehash: 953acc32c3510b31c265f2d64d0a013f6dee06cc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372888"
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC Sınıf Nesnelerine İlişkin Tür Atama

Tür döküm makroları, dökümün yasal olup olmadığını kontrol etmekle veya denetlemeden belirli bir işaretçiyi belirli bir sınıfın nesnesine işaret eden bir işaretçiye atmanın bir yolunu sağlar.

Aşağıdaki tabloda MFC tipi döküm makroları listelenir.

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>İşaretçileri MFC Sınıf Nesnelerine Atan Makrolar

|||
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Dökümyasal olup olmadığını kontrol ederken bir sınıf nesnesi için bir işaretçi atar.|
|[STATIC_DOWNCAST](#static_downcast)|Bir nesneye işaretçi atar, bir sınıftan ilgili türdeki bir işaretçiye. Hata ayıklama yapısında, nesne hedef türü "tür" değilse, bir Assert neden olur.|

## <a name="dynamic_downcast"></a><a name="dynamic_downcast"></a>DYNAMIC_DOWNCAST

Döküm yasal olup olmadığını kontrol ederken bir işaretçi bir sınıf nesnesine bir işaretçi döküm kullanışlı bir yol sağlar.

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>Parametreler

*sınıf*<br/>
Bir sınıfın adı.

*pointer*<br/>
Bir işaretçi türü *sınıfının*bir nesneye işaretçi için döküm için .

### <a name="remarks"></a>Açıklamalar

Makro, *işaretçi* parametresini *sınıf* parametresinin türündeki bir nesneye işaretçiye atar.

İşaretçi tarafından başvurulan nesne tanımlanan sınıf "tür" ise, makro uygun işaretçidöndürür. Yasal bir döküm değilse, makro NULL döndürür.

## <a name="static_downcast"></a><a name="static_downcast"></a>STATIC_DOWNCAST

Bir *işaretçiye* *class_name* bir nesneye pobject atar.

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Atan sınıfın adı.

*Pobject*<br/>
Bir *class_name* nesneye işaretçiye atanacak işaretçi.

### <a name="remarks"></a>Açıklamalar

*pobject* ya NULL olmalı, ya da doğrudan veya dolaylı olarak, *class_name*türetilmiş bir sınıfın bir nesneye işaret . Tanımlanan _DEBUG önişlemci simgesiyle uygulamanızın yapılarında, *makro, pobject* NULL değilse veya *class_name* parametresinde belirtilen sınıfa "tür" olmayan bir nesneyi işaret ederse,(bkz. [CObject:IsKindOf).](../../mfc/reference/cobject-class.md#iskindof) **_DEBUG** olmayan yapılarda, makro herhangi bir tür denetimi olmadan döküm gerçekleştirir.

*class_name* parametresinde belirtilen sınıf, `CObject` [CObject Class: CObject'ten Bir Sınıf Türeyen](../../mfc/deriving-a-class-from-cobject.md)DECLARE_DYNAMIC ve IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE ve IMPLEMENT_DYNCREATE veya DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarından türetilmeli ve kullanılmalıdır.

Örneğin, bu ifadeyi kullanmak `CMyDoc`için `pMyDoc`bir işaretçiye işaretçi atabilirsiniz: `CDocument`

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

Doğrudan `pMyDoc` veya dolaylı olarak türetilen bir `CDocument`nesneye işaret etmiyorsa, makro Assert olacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
