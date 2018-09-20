---
title: CTypedPtrList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 758be6cfec0c4d70ebf632eaf90e3623632ffbe5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417521"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList sınıfı

Sınıfındaki nesneler için tür açısından güvenli bir "sarmalayıcı" sağlar `CPtrList`.

## <a name="syntax"></a>Sözdizimi

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>Parametreler

*$BASE_CLASS*<br/>
Türü belirtilmiş işaretçi liste sınıfın temel sınıfına; bir işaretçi liste sınıfı olmalıdır ( `CObList` veya `CPtrList`).

*TÜRÜ*<br/>
Temel sınıf listesinde depolanan öğelerin türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTypedPtrList::AddHead](#addhead)|Bir öğenin (veya başka bir listedeki tüm öğeleri) (yeni head sağlar) listenin başındaki ekler.|
|[CTypedPtrList::AddTail](#addtail)|Bir öğenin (veya başka bir listedeki tüm öğeleri) (yeni bir kuyruk sağlar) listesi kuyruğu için ekler.|
|[CTypedPtrList::GetAt](#getat)|Öğesini, belirli bir konumda alır.|
|[CTypedPtrList::GetHead](#gethead)|Head öğesi (boş olamaz) listesi döndürür.|
|[CTypedPtrList::GetNext](#getnext)|Yineleme için sonraki öğeyi alır.|
|[CTypedPtrList::GetPrev](#getprev)|Yineleme için önceki öğeyi alır.|
|[CTypedPtrList::GetTail](#gettail)|Kuyruk öğesini (boş olamaz) listesi döndürür.|
|[CTypedPtrList::RemoveHead](#removehead)|Öğe listesinin başından kaldırır.|
|[CTypedPtrList::RemoveTail](#removetail)|Öğe listesinin kuyruğunu kaldırır.|
|[CTypedPtrList::SetAt](#setat)|Öğe, belirli bir konumda ayarlar.|

## <a name="remarks"></a>Açıklamalar

Kullanırken `CTypedPtrList` yerine `CObList` veya `CPtrList`, C++ tür denetimi olanağı eşleşmeyen işaretçi türleri tarafından neden olduğu hata ortadan yardımcı olur.

Ayrıca, `CTypedPtrList` sarmalayıcı kullandıysanız, gerekli olacak atama çoğunu gerçekleştirir `CObList` veya `CPtrList`.

Çünkü tüm `CTypedPtrList` satır içi işlevlerdir, bu şablonun kullanımını boyut veya hız kodunuzun önemli ölçüde etkilemez.

Listeleri türetilen `CObList` , ancak bu türetilen seri hale getirilebilir `CPtrList` olamaz.

Olduğunda bir `CTypedPtrList` nesnesi silindiğinde veya yalnızca işaretçiler öğelerine kaldırıldığında kaldırılır, bunlar başvuru varlıkları.

Kullanma hakkında daha fazla bilgi için `CTypedPtrList`, makalelere göz atın [koleksiyonları](../../mfc/collections.md) ve [şablona dayalı sınıflar](../../mfc/template-based-classes.md).

## <a name="example"></a>Örnek

Bu örnek, bir örneğini oluşturur. `CTypedPtrList`, bir nesne ekler, disk listeye serileştirir ve sonra nesneyi siler:

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtempl.h

##  <a name="addhead"></a>  CTypedPtrList::AddHead

Bu üye işlevini çağırır `BASE_CLASS` **:: AddHead**.

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Temel sınıf listesinde depolanan öğelerin türü.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi. NULL değerine izin verilir.

*$BASE_CLASS*<br/>
Türü belirtilmiş işaretçi liste sınıfın temel sınıfına; bir işaretçi liste sınıfı olmalıdır ( [CObList](../../mfc/reference/coblist-class.md) veya [CPtrList](../../mfc/reference/cptrlist-class.md)).

*pNewList*<br/>
Başka bir işaretçiye [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) nesne. Öğeleri *pNewList* bu listeye eklenir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürümü, yeni eklenen öğenin KONUMUNU değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm, listenin başındaki önce yeni bir öğe ekler. Dosyanın ikinci sürümü baş önce öğeleri başka bir listesini ekler.

##  <a name="addtail"></a>  CTypedPtrList::AddTail

Bu üye işlevini çağırır `BASE_CLASS` **:: AddTail**.

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Temel sınıf listesinde depolanan öğelerin türü.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi. NULL değerine izin verilir.

*$BASE_CLASS*<br/>
Türü belirtilmiş işaretçi liste sınıfın temel sınıfına; bir işaretçi liste sınıfı olmalıdır ( [CObList](../../mfc/reference/coblist-class.md) veya [CPtrList](../../mfc/reference/cptrlist-class.md)).

*pNewList*<br/>
Başka bir işaretçiye [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) nesne. Öğeleri *pNewList* bu listeye eklenir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürümü, yeni eklenen öğenin KONUMUNU değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm listesi kuyruğunu sonra yeni bir öğe ekler. Dosyanın ikinci sürümü listesinin kuyruğunu sonra başka bir öğe listesi ekler.

##  <a name="getat"></a>  CTypedPtrList::GetAt

KONUM türünde bir değişken listesi için bir anahtardır.

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Şablon parametresi belirtme listesinde depolanan öğelerin türü.

*Konumu*<br/>
Bir önceki tarafından döndürülen bir konum değeri `GetHeadPosition` veya `Find` üye işlev çağrısı.

### <a name="return-value"></a>Dönüş Değeri

Listenin işaretçi üzerinden erişiliyorsa bir `const CTypedPtrList`, ardından `GetAt` şablon parametresi tarafından belirtilen türde bir işaretçi döndürür *türü*. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece liste değişikliklere karşı korur.

Listeden doğrudan veya bir işaretçiyle çok erişildiği durumda bir `CTypedPtrList`, ardından `GetAt` bir şablon parametresi tarafından belirtilen türde bir işaretçi başvurusu döndürür *türü*. Bu işlev, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

### <a name="remarks"></a>Açıklamalar

Bu dizin ile aynı değildir ve üzerinde bir konum değeri kendiniz çalışamaz. `GetAt` alır `CObject` işaretçi verilen bir konumu ile ilişkili.

KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

Bu satır içi işlev çağrıları `BASE_CLASS` **:: GetAt**.

##  <a name="gethead"></a>  CTypedPtrList::GetHead

Head öğesi, bu listenin temsil eden bir işaretçi alır.

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Şablon parametresi belirtme listesinde depolanan öğelerin türü.

### <a name="return-value"></a>Dönüş Değeri

Listenin işaretçi üzerinden erişiliyorsa bir `const CTypedPtrList`, ardından `GetHead` şablon parametresi tarafından belirtilen türde bir işaretçi döndürür *türü*. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece liste değişikliklere karşı korur.

Listeden doğrudan veya bir işaretçiyle çok erişildiği durumda bir `CTypedPtrList`, ardından `GetHead` bir şablon parametresi tarafından belirtilen türde bir işaretçi başvurusu döndürür *türü*. Bu işlev, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

### <a name="remarks"></a>Açıklamalar

Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `GetHead`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](../../mfc/reference/coblist-class.md#isempty) liste öğeleri içerdiğini doğrulayın.

##  <a name="getnext"></a>  CTypedPtrList::GetNext

Tarafından tanımlanan liste öğesi alır *rPosition*, ardından ayarlar *rPosition* için listedeki sonraki giriş konum değeri.

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Şablon parametresi bu listede yer alan öğelerin türünü belirtme.

*rPosition*<br/>
Bir önceki tarafından döndürülen bir konum değeri başvurusu `GetNext`, `GetHeadPosition`, ya da diğer üye işlev çağrısı.

### <a name="return-value"></a>Dönüş Değeri

Listenin işaretçi üzerinden erişiliyorsa bir `const CTypedPtrList`, ardından `GetNext` şablon parametresi tarafından belirtilen türde bir işaretçi döndürür *türü*. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece liste değişikliklere karşı korur.

Listeden doğrudan veya bir işaretçiyle çok erişildiği durumda bir `CTypedPtrList`, ardından `GetNext` bir şablon parametresi tarafından belirtilen türde bir işaretçi başvurusu döndürür *türü*. Bu işlev, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

### <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz `GetNext` çağrısıyla ilk konumunu kurarsanız ileriye doğru yineleme döngüsünde `GetHeadPosition` veya [CPtrList::Find](../../mfc/reference/coblist-class.md#find).

KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

Alınan öğe listesinde, son öğesinin yeni değeri ise *rPosition* NULL olarak ayarlandı.

Bir yineleme sırasında bir öğe kaldırmak mümkündür. Örneğin bakın [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat).

##  <a name="getprev"></a>  CTypedPtrList::GetPrev

Tarafından tanımlanan liste öğesi alır *rPosition*, ardından ayarlar *rPosition* konumu değerine listesinde önceki girişi.

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Şablon parametresi bu listede yer alan öğelerin türünü belirtme.

*rPosition*<br/>
Bir önceki tarafından döndürülen bir konum değeri başvurusu `GetPrev` veya diğer üye işlev çağrısı.

### <a name="return-value"></a>Dönüş Değeri

Listenin işaretçi üzerinden erişiliyorsa bir `const CTypedPtrList`, ardından `GetPrev` şablon parametresi tarafından belirtilen türde bir işaretçi döndürür *türü*. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece liste değişikliklere karşı korur.

Listeden doğrudan veya bir işaretçiyle çok erişildiği durumda bir `CTypedPtrList`, ardından `GetPrev` bir şablon parametresi tarafından belirtilen türde bir işaretçi başvurusu döndürür *türü*. Bu işlev, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

### <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz `GetPrev` çağrısıyla ilk konumunu kurarsanız geriye doğru yineleme döngüsünde `GetTailPosition` veya `Find`.

KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

Alınan öğe listesinde ilk yeni değeri ise *rPosition* NULL olarak ayarlandı.

##  <a name="gettail"></a>  CTypedPtrList::GetTail

Head öğesi, bu listenin temsil eden bir işaretçi alır.

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Şablon parametresi belirtme listesinde depolanan öğelerin türü.

### <a name="return-value"></a>Dönüş Değeri

Listenin işaretçi üzerinden erişiliyorsa bir `const CTypedPtrList`, ardından `GetTail` şablon parametresi tarafından belirtilen türde bir işaretçi döndürür *türü*. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece liste değişikliklere karşı korur.

Listeden doğrudan veya bir işaretçiyle çok erişildiği durumda bir `CTypedPtrList`, ardından `GetTail` bir şablon parametresi tarafından belirtilen türde bir işaretçi başvurusu döndürür *türü*. Bu işlev, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

### <a name="remarks"></a>Açıklamalar

Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `GetTail`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](../../mfc/reference/coblist-class.md#isempty) liste öğeleri içerdiğini doğrulayın.

##  <a name="removehead"></a>  CTypedPtrList::RemoveHead

Öğe listesinin başından kaldırır ve döndürür.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Şablon parametresi belirtme listesinde depolanan öğelerin türü.

### <a name="return-value"></a>Dönüş Değeri

Daha önce listesinin sonunda işaretçisi. Bu şablon parametresi tarafından belirtilen tür işaretçisidir *türü*.

### <a name="remarks"></a>Açıklamalar

Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `RemoveHead`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](../../mfc/reference/coblist-class.md#isempty) liste öğeleri içerdiğini doğrulayın.

##  <a name="removetail"></a>  CTypedPtrList::RemoveTail

Listenin kuyruğunu öğeyi kaldırır ve döndürür.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Parametreler

*TÜRÜ*<br/>
Şablon parametresi belirtme listesinde depolanan öğelerin türü.

### <a name="return-value"></a>Dönüş Değeri

Daha önce listenin sonu işaretçisi. Bu şablon parametresi tarafından belirtilen tür işaretçisidir *türü*.

### <a name="remarks"></a>Açıklamalar

Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `RemoveTail`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](../../mfc/reference/coblist-class.md#isempty) liste öğeleri içerdiğini doğrulayın.

##  <a name="setat"></a>  CTypedPtrList::SetAt

Bu üye işlevini çağırır `BASE_CLASS` **:: SetAt**.

```
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Ayarlanacak öğenin konumu.

*TÜRÜ*<br/>
Temel sınıf listesinde depolanan öğelerin türü.

*newElement*<br/>
Listesine yazılacak nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

KONUM türünde bir değişken listesi için bir anahtardır. Bu dizin ile aynı değildir ve üzerinde bir konum değeri kendiniz çalışamaz. `SetAt` nesne işaretçisi listede belirtilen konuma yazar.

KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

Daha ayrıntılı açıklamalar için bkz. [CObList::SetAt](../../mfc/reference/coblist-class.md#setat).

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek Topla](../../visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPtrList Sınıfı](../../mfc/reference/cptrlist-class.md)<br/>
[CObList Sınıfı](../../mfc/reference/coblist-class.md)
