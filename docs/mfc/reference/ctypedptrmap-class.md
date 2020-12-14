---
description: 'Daha fazla bilgi edinin: CTypedPtrMap sınıfı'
title: CTypedPtrMap sınıfı
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
ms.openlocfilehash: 25476a9195fe4a522ed31937dc1e2c5156ef6792
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344997"
---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap sınıfı

İşaretçi eşleme sınıflarının `CMapPtrToPtr` ,, `CMapPtrToWord` `CMapWordToPtr` , ve nesneleri için tür açısından güvenli bir "sarmalayıcı" sağlar `CMapStringToPtr` .

## <a name="syntax"></a>Sözdizimi

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Türü belirtilmiş işaretçi eşleme sınıfının temel sınıfı; bir işaretçi eşleme sınıfı olmalıdır ( `CMapPtrToPtr` , `CMapPtrToWord` , `CMapWordToPtr` veya `CMapStringToPtr` ).

*ANAHTAR*<br/>
Haritada anahtar olarak kullanılan nesnenin sınıfı.

*VALUE*<br/>
Haritada depolanan nesnenin sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTypedPtrMap:: GetNextAssoc](#getnextassoc)|Yineleme için bir sonraki öğeyi alır.|
|[CTypedPtrMap:: Lookup](#lookup)|Temelinde bir döndürür `KEY` `VALUE` .|
|[CTypedPtrMap:: RemoveKey](#removekey)|Anahtar tarafından belirtilen öğeyi kaldırır.|
|[CTypedPtrMap:: SetAt](#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğeyi değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CTypedPtrMap:: işleci \[\]](#operator_at)|Haritaya bir öğe ekler.|

## <a name="remarks"></a>Açıklamalar

Kullandığınızda `CTypedPtrMap` , C++ tür denetimi özelliği, eşleşmeyen işaretçi türleri nedeniyle oluşan hataları ortadan kaldırmaya yardımcı olur.

Tüm `CTypedPtrMap` işlevler satır içi olduğundan, bu şablonun kullanımı kodunuzun boyutunu veya hızını önemli ölçüde etkilemez.

Kullanma hakkında daha fazla bilgi için `CTypedPtrMap` bkz. Makale [koleksiyonları](../../mfc/collections.md) ve [şablon tabanlı sınıflar](../../mfc/template-based-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtempl. h

## <a name="ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a> CTypedPtrMap:: GetNextAssoc

Konumundaki Map öğesini alır `rNextPosition` ve ardından `rNextPosition` haritadaki bir sonraki öğeye başvuracak şekilde günceller.

```cpp
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*rPosition*<br/>
Previous `GetNextAssoc` veya `BASE_CLASS` **:: GetStartPosition** ÇAĞRıSı tarafından döndürülen bir konum değerine bir başvuru belirtir.

*ANAHTAR*<br/>
Harita anahtarlarının türünü belirten şablon parametresi.

*rKey*<br/>
Alınan öğenin döndürülen anahtarını belirtir.

*VALUE*<br/>
Haritanın değerlerinin türünü belirten şablon parametresi.

*Başvurusuna*<br/>
Alınan öğenin döndürülen değerini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, haritadaki tüm öğeler arasında yineleme için en yararlı seçenektir. Konum sırasının, anahtar değer sırasıyla aynı olması gerekmediğini unutmayın.

Alınan öğe haritada son ise, yeni değeri `rNextPosition` null olarak ayarlanır.

Bu satır içi işlev `BASE_CLASS` **:: GetNextAssoc** öğesini çağırır.

## <a name="ctypedptrmaplookup"></a><a name="lookup"></a> CTypedPtrMap:: Lookup

`Lookup` , tam olarak eşleşen bir anahtarla Map öğesini hızlı bir şekilde bulmak için bir karma algoritması kullanır.

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Bu haritanın sınıfının temel sınıfını belirten şablon parametresi.

*anahtar*<br/>
Aranacak öğenin anahtarı.

*VALUE*<br/>
Bu haritada depolanan değerlerin türünü belirten şablon parametresi.

*Başvurusuna*<br/>
Alınan öğenin döndürülen değerini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu satır içi işlev `BASE_CLASS` **:: Lookup** öğesini çağırır.

## <a name="ctypedptrmapoperator--"></a><a name="operator_at"></a> CTypedPtrMap:: operator []

Bu işleç yalnızca bir atama ifadesinin (bir l-değer) sol tarafında kullanılabilir.

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>Parametreler

*VALUE*<br/>
Bu haritada depolanan değerlerin türünü belirten şablon parametresi.

*BASE_CLASS*<br/>
Bu haritanın sınıfının temel sınıfını belirten şablon parametresi.

*anahtar*<br/>
Haritada aranacak veya oluşturulacak öğenin anahtarı.

### <a name="remarks"></a>Açıklamalar

Belirtilen anahtara sahip bir eşleme öğesi yoksa, yeni bir öğe oluşturulur. Haritada bir anahtarın bulunamaması olasılığı olduğu için bu işlece "sağ taraf" (r-değer) eşdeğeri yoktur. `Lookup`Öğe alımı için üye işlevini kullanın.

## <a name="ctypedptrmapremovekey"></a><a name="removekey"></a> CTypedPtrMap:: RemoveKey

Bu üye işlevi şunu çağırır `BASE_CLASS` **:: RemoveKey**.

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>Parametreler

*ANAHTAR*<br/>
Harita anahtarlarının türünü belirten şablon parametresi.

*anahtar*<br/>
Kaldırılacak öğe için anahtar.

### <a name="return-value"></a>Dönüş Değeri

Giriş bulunursa ve başarıyla kaldırılmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CMapStringToOb:: RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).

## <a name="ctypedptrmapsetat"></a><a name="setat"></a> CTypedPtrMap:: SetAt

Bu üye işlevi `BASE_CLASS` **:: SetAt** çağırır.

```cpp
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>Parametreler

*ANAHTAR*<br/>
Harita anahtarlarının türünü belirten şablon parametresi.

*anahtar*<br/>
NewValue öğesinin anahtar değerini belirtir.

*Değer*<br/>
Yeni öğenin değeri olan nesne işaretçisini belirtir.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CMapStringToOb:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek toplama](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr sınıfı](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord sınıfı](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapWordToPtr sınıfı](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[CMapStringToPtr sınıfı](../../mfc/reference/cmapstringtoptr-class.md)
