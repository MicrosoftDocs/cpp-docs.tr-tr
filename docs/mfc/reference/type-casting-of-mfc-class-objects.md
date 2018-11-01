---
title: MFC Sınıf Nesnelerine İlişkin Tür Atama
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.classes
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
ms.openlocfilehash: 42b668287905fc5f6e05a09949d53acc51c79026
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584151"
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC Sınıf Nesnelerine İlişkin Tür Atama

Tür atama makroları ile veya olmadan cast geçerli olup olmadığını denetleyerek belirli sınıfının bir nesneye işaret eden bir işaretçi verilen bir işaretçiye için bir yol sağlar.

Aşağıdaki tabloda, MFC tür atama makroları listeler.

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>MFC sınıf nesnelerine işaretçiler atama makroları

|||
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Bir sınıf nesnesine bir işaretçi işaretçisi dönüştürme geçerli olup olmadığını denetlerken çevirir.|
|[STATIC_DOWNCAST](#static_downcast)|Bir işaretçi bir nesne için bir sınıftan ilgili türünde bir işaretçiye çevirir. Nesne değilse, hata ayıklama yapısında, bir onay neden olan bir "tür" hedef türü.|

##  <a name="dynamic_downcast"></a>  DYNAMIC_DOWNCAST

Bir sınıf nesnesine bir işaretçi dönüştürme geçerli olup olmadığını denetlerken işaretçiye için kullanışlı bir yol sağlar.

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>Parametreler

*class*<br/>
Bir sınıfın adı.

*İşaretçi*<br/>
Bir işaretçi işaretçisi türünde bir nesne başvurusuna *sınıfı*.

### <a name="remarks"></a>Açıklamalar

Makro cast *işaretçi* parametresi bir nesnenin işaretçisi *sınıfı* parametrenin türü.

İşaretçi tarafından başvurulan nesne ise, bir "tür" tanımlanan sınıfı makro uygun işaretçiyi döndürür. Yasal bir yayın değil ise, makro NULL döndürür.

##  <a name="static_downcast"></a>  STATIC_DOWNCAST

Yayınları *pobject* işaretçisi bir *$class_name* nesne.

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Dönüştürme için sınıfı adı.

*pobject*<br/>
İşaretçiyi bir işaretçiye dönüştürülebilir bir *$class_name* nesne.

### <a name="remarks"></a>Açıklamalar

*pobject* gerekir ya da NULL olamaz ya da doğrudan türetilmiş bir sınıfın veya dolaylı olarak gelen bir nesneye işaret *$class_name*. Tanımlanan _DEBUG önişlemci sembolü uygulamanızla yapılarında makrosu, İDDİA *pobject* NULL değil veya olmayan bir nesneye işaret ediyorsa bir "tür" Belirtilen sınıf *$class_name*parametre (bkz [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof)). İçinde olmayan **_DEBUG** yapılar, makrosu, herhangi bir tür denetlemesi olmadan cast gerçekleştirir.

Belirtilen sınıf *$class_name* parametresi türetilen gerekir `CObject` DECLARE_DYNAMIC ımplement_dynamıc, DECLARE_DYNCREATE ve IMPLEMENT_DYNCREATE, veya declare_serıal ve IMPLEMENT_ kullanmalıdır Seri makroları olarak makalesinde açıklanan [CObject sınıfı: CObject'ten sınıf türetme](../../mfc/deriving-a-class-from-cobject.md).

Örneğin, bir işaretçiye dönüştürme `CMyDoc`adlı `pMyDoc`, işaretçisi `CDocument` Bu ifade kullanarak:

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

Varsa `pMyDoc` doğrudan veya dolaylı olarak türetilmiş bir nesneye işaret etmiyor `CDocument`, makro ASSERT.

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
