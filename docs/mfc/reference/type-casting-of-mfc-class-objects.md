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
ms.openlocfilehash: e3702ced83021e42ac6bf71a78efc51fa07b8be9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840498"
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC Sınıf Nesnelerine İlişkin Tür Atama

Tür atama makroları, belirli bir işaretçinin bir nesneye işaret eden bir işaretçiye, dönüştürmenin yasal olduğunu denetlemeden veya denetlemeden işaret eden bir işaretçiye dönüştürmek için bir yol sağlar.

Aşağıdaki tabloda MFC türü atama makroları listelenmektedir.

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>MFC sınıf nesnelerine Işaretçiler atama yapan makrolar

|Ad|Açıklama|
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|Dönüştürmenin yasal olup olmadığını denetlerken, bir sınıf nesnesine bir işaretçi işaretçisi yayınlar.|
|[STATIC_DOWNCAST](#static_downcast)|Bir nesnenin işaretçisini bir sınıftan ilgili türün işaretçisine yayınlar. Bir hata ayıklama derlemesinde, nesne hedef türü "tür" değilse bir onaylama olur.|

## <a name="dynamic_downcast"></a><a name="dynamic_downcast"></a> DYNAMIC_DOWNCAST

Dönüştürmenin yasal olup olmadığını denetlerken, bir işaretçiyi bir sınıf nesnesine işaretçiye dönüştürmek için kullanışlı bir yol sağlar.

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>Parametreler

*sınıfı*<br/>
Bir sınıfın adı.

*pointer*<br/>
*Sınıf*türündeki bir nesneye bir işaretçiye dönüştürme işaretçisi.

### <a name="remarks"></a>Açıklamalar

Makro, *işaretçi* parametresini *sınıf* parametresi türünün bir nesnesine bir işaretçiye saçacaktır.

İşaretçi tarafından başvurulan nesne, tanımlı sınıf olan "tür" ise, makro uygun işaretçiyi döndürür. Geçerli bir atama değilse, makro NULL değerini döndürür.

## <a name="static_downcast"></a><a name="static_downcast"></a> STATIC_DOWNCAST

*Class_name* nesnesine bir işaretçiye *nesnesini* yayınlar.

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Üzerine aktarılmakta olan sınıfın adı.

*nesnesini*<br/>
*Class_name* nesnesine bir işaretçiye dönüştürme işaretçisi.

### <a name="remarks"></a>Açıklamalar

*nesnesini* null olmalıdır veya doğrudan veya dolaylı olarak türetilmiş bir sınıfın nesnesine işaret etmelidir *class_name*. _DEBUG Önişlemci simgesiyle uygulamanızın Derlemeleriyle, *nesnesini* null değilse veya *class_name* parametresinde belirtilen sınıf "türü" olmayan bir nesneye işaret ediyorsa (bkz. [CObject:: iskindof](../../mfc/reference/cobject-class.md#iskindof)). **_DEBUG** olmayan derlemelerde, makro herhangi bir tür denetlemesi olmadan atama işlemini gerçekleştirir.

*Class_name* parametresinde belirtilen sınıf öğesinden türetilmeli `CObject` ve DECLARE_DYNAMIC ve IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE ve IMPLEMENT_DYNCREATE veya DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarını kullanarak CObject [Sınıfı: CObject sınıfından bir sınıf türetiliyor](../../mfc/deriving-a-class-from-cobject.md).

Örneğin, `CMyDoc` `pMyDoc` Bu ifadeyi kullanmak için bir işaretçi olarak adlandırılan bir işaretçiye çevirebilirsiniz `CDocument` :

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

`pMyDoc`Doğrudan veya dolaylı olarak türetilmiş bir nesneyi işaret etmez `CDocument` , makro onay olacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
