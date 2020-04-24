---
title: CTypedPtrMap Sınıfı
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
ms.openlocfilehash: 410f0101fd0f8cda271fe0f2353b06b9e8d773b8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754370"
---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap Sınıfı

İşaretçi-eşlemi `CMapPtrToPtr`sınıflarının nesneleri için tür güvenli bir `CMapPtrToWord` `CMapWordToPtr`"sarmalayıcı" sağlar, , , ve `CMapStringToPtr`.

## <a name="syntax"></a>Sözdizimi

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Yazılan işaretçi eşlemi sınıfının taban sınıfı; işaretçi eşlemi `CMapPtrToPtr`sınıfı `CMapPtrToWord` `CMapWordToPtr`olmalıdır `CMapStringToPtr`( , , , veya ).

*Anahtar*<br/>
Haritanın anahtarı olarak kullanılan nesnenin sınıfı.

*Değer*<br/>
Haritada depolanan nesnenin sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Yinelenmenin bir sonraki öğesini alır.|
|[CTypedPtrMap::Arama](#lookup)|Bir `KEY` ' ye `VALUE`dayalı bir verir.|
|[CTypedPtrMap::RemoveKey](#removekey)|Anahtar tarafından belirtilen bir öğeyi kaldırır.|
|[CTypedPtrMap::SetAt](#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğenin yerini alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CTypedPtrMap::operatör \[\]](#operator_at)|Eşme bir öğe ekler.|

## <a name="remarks"></a>Açıklamalar

C++ `CTypedPtrMap`tür denetleme tesisi kullandığınızda, eşleşmeyan işaretçi türlerinin neden olduğu hataların giderilmesine yardımcı olur.

Tüm `CTypedPtrMap` işlevler satır lı olduğundan, bu şablonun kullanımı kodunuzun boyutunu veya hızını önemli ölçüde etkilemez.

Kullanma `CTypedPtrMap`hakkında daha fazla bilgi için [Koleksiyonlar](../../mfc/collections.md) ve [Şablon Tabanlı Sınıflar](../../mfc/template-based-classes.md)makalelerine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtempl.h

## <a name="ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a>CTypedPtrMap::GetNextAssoc

Harita öğesini `rNextPosition`alır, sonra `rNextPosition` haritadaki bir sonraki öğeye başvurmak için güncellenir.

```cpp
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*Rposition*<br/>
Bir önceki `GetNextAssoc` veya `BASE_CLASS` **::GetStartPosition** çağrısı tarafından döndürülen bir POSITION değerine başvuru belirtir.

*Anahtar*<br/>
Haritanın anahtarlarının türünü belirten şablon parametresi.

*rAnahtar*<br/>
Alınan öğenin döndürülen anahtarını belirtir.

*Değer*<br/>
Eşleme değerlerinin türünü belirten şablon parametresi.

*Rvalue*<br/>
Alınan öğenin döndürülen değerini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, haritadaki tüm öğeleri yineetmek için en yararlıdır. Konum sırasının anahtar değer dizisiyle aynı olması gerekmediğini unutmayın.

Alınan öğe haritadaki son `rNextPosition` öğeyse, yeni değeri NULL olarak ayarlanır.

Bu satır lı `BASE_CLASS`fonksiyon çağırır **::GetNextAssoc**.

## <a name="ctypedptrmaplookup"></a><a name="lookup"></a>CTypedPtrMap::Arama

`Lookup`harita öğesini tam olarak eşleşen bir anahtarla hızla bulmak için karma algoritması kullanır.

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Bu haritanın sınıfının taban sınıfını belirten şablon parametresi.

*anahtar*<br/>
Eleman anahtarı aranır.

*Değer*<br/>
Bu haritada depolanan değerlerin türünü belirten şablon parametresi.

*Rvalue*<br/>
Alınan öğenin döndürülen değerini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunursa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu satır ara `BASE_CLASS`işlevi çağırır **::Arama**.

## <a name="ctypedptrmapoperator--"></a><a name="operator_at"></a>CTypedPtrMap::operatör [ ]

Bu işleç yalnızca bir atama deyiminin (l-değeri) sol tarafında kullanılabilir.

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Bu haritada depolanan değerlerin türünü belirten şablon parametresi.

*BASE_CLASS*<br/>
Bu haritanın sınıfının taban sınıfını belirten şablon parametresi.

*anahtar*<br/>
Öğenin anahtar aranır veya haritada oluşturulacak.

### <a name="remarks"></a>Açıklamalar

Belirtilen anahtara sahip bir eş öğesi yoksa, yeni bir öğe oluşturulur. Haritada bir anahtarın bulunmama olasılığı olduğundan, bu işleçiçin "sağ taraf" (r-değeri) yoktur. Öğe `Lookup` almak için üye işlevi kullanın.

## <a name="ctypedptrmapremovekey"></a><a name="removekey"></a>CTypedPtrMap::RemoveKey

Bu üye `BASE_CLASS`işlev **::RemoveKey**.

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>Parametreler

*Anahtar*<br/>
Haritanın anahtarlarının türünü belirten şablon parametresi.

*anahtar*<br/>
Öğenin kaldırılması için anahtar.

### <a name="return-value"></a>Dönüş Değeri

Giriş bulundu ve başarıyla kaldırıldı sıfır değil; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için [Bkz. CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).

## <a name="ctypedptrmapsetat"></a><a name="setat"></a>CTypedPtrMap::SetAt

Bu üye `BASE_CLASS`işlev **::SetAt.**

```cpp
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>Parametreler

*Anahtar*<br/>
Haritanın anahtarlarının türünü belirten şablon parametresi.

*anahtar*<br/>
newValue'ın anahtar değerini belirtir.

*Newvalue*<br/>
Yeni öğenin değeri olan nesne işaretçisini belirtir.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için [Bkz. CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TOPLAMA](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr Sınıfı](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord Sınıfı](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapWordToPtr Sınıfı](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[CMapStringToPtr Sınıfı](../../mfc/reference/cmapstringtoptr-class.md)
