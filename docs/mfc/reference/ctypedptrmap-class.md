---
title: CTypedPtrMap Class
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
ms.openlocfilehash: bc164125f867cf3e2f27b74e69b826cbed31ff1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323576"
---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap Class

Bir tür açısından güvenli, işaretçi eşleme sınıflarındaki nesneler için "sarmalayıcı" sağlar `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, ve `CMapStringToPtr`.

## <a name="syntax"></a>Sözdizimi

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Türü belirtilmiş işaretçi eşleme sınıfının temel sınıfı; bir işaretçi eşlem sınıfı olmalıdır ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, veya `CMapStringToPtr`).

*KEY*<br/>
Harita anahtarı olarak kullanılan nesne sınıfı.

*DEĞER*<br/>
Eşlem içinde depolan bir nesne sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Yineleme için sonraki öğeyi alır.|
|[CTypedPtrMap::Lookup](#lookup)|Döndürür bir `KEY` dayalı bir `VALUE`.|
|[CTypedPtrMap::RemoveKey](#removekey)|Bir anahtar tarafından belirtilen bir öğeyi kaldırır.|
|[CTypedPtrMap::SetAt](#setat)|Haritayı bir öğe ekler; eşleşen bir anahtar bulunursa, var olan öğenin yerini alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CTypedPtrMap::operator \[ \]](#operator_at)|Haritayı bir öğe ekler.|

## <a name="remarks"></a>Açıklamalar

Kullanırken `CTypedPtrMap`, C++ tür denetimi olanağı eşleşmeyen işaretçi türleri tarafından neden olduğu hata ortadan yardımcı olur.

Çünkü tüm `CTypedPtrMap` satır içi işlevlerdir, bu şablonun kullanımını boyut veya hız kodunuzun önemli ölçüde etkilemez.

Kullanma hakkında daha fazla bilgi için `CTypedPtrMap`, makalelere göz atın [koleksiyonları](../../mfc/collections.md) ve [şablona dayalı sınıflar](../../mfc/template-based-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtempl.h

##  <a name="getnextassoc"></a>  CTypedPtrMap::GetNextAssoc

Harita öğe alır `rNextPosition`, ardından güncelleştirmeleri `rNextPosition` haritadaki sonraki öğeye başvurmak için.

```
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*rPosition*<br/>
Bir önceki tarafından döndürülen bir konum değeri bir başvuru belirtir `GetNextAssoc` veya `BASE_CLASS` **:: GetStartPosition** çağırın.

*KEY*<br/>
Haritanın anahtarları türünü belirten bir şablon parametre.

*rKey*<br/>
Alınan öğenin döndürülen anahtarını belirtir.

*DEĞER*<br/>
Şablon parametresi türü haritanın değerler belirtme.

*rValue*<br/>
Alınan öğenin döndürülen değeri belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir eşlem içindeki tüm öğeleri arasında yineleme için kullanışlıdır. Konumu sıranın mutlaka anahtar değeri serisi ile aynı olmadığını unutmayın.

Alınan öğe eşlem içindeki son öğesinin yeni değeri ise `rNextPosition` NULL olarak ayarlandı.

Bu satır içi işlev çağrıları `BASE_CLASS` **:: GetNextAssoc**.

##  <a name="lookup"></a>  CTypedPtrMap::Lookup

`Lookup` eşleme öğesi tam olarak eşleşen bir anahtar ile hızla bulmak için bir karma algoritma kullanır.

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Şablon parametresi bu haritanın sınıfın temel sınıfına belirtme.

*anahtar*<br/>
Bakılacak öğenin anahtarı.

*DEĞER*<br/>
Şablon parametresi bu eşlemesinde depolanan değerlerin türü belirtme.

*rValue*<br/>
Alınan öğenin döndürülen değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Öğesi bulundu; olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu satır içi işlev çağrıları `BASE_CLASS` **:: arama**.

##  <a name="operator_at"></a>  CTypedPtrMap::operator]

Bu işleç, yalnızca (lvalue) atama deyiminin sol tarafında kullanılabilir.

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>Parametreler

*DEĞER*<br/>
Şablon parametresi bu eşlemesinde depolanan değerlerin türü belirtme.

*BASE_CLASS*<br/>
Şablon parametresi bu haritanın sınıfın temel sınıfına belirtme.

*anahtar*<br/>
Aranan ya da haritada oluşturulan öğenin anahtarı.

### <a name="remarks"></a>Açıklamalar

Ardından, belirtilen anahtara sahip herhangi bir harita öğe varsa, yeni bir öğe oluşturulur. Yoktur yok "sağ tarafında" (r) bu operatörü için eşdeğeri anahtar haritada bulunamamış olabilir bir olasılık olduğundan. Kullanım `Lookup` öğesi alma için üye işlevi.

##  <a name="removekey"></a>  CTypedPtrMap::RemoveKey

Bu üye işlevini çağırır `BASE_CLASS` **:: RemoveKey**.

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>Parametreler

*KEY*<br/>
Haritanın anahtarları türünü belirten bir şablon parametre.

*anahtar*<br/>
Kaldırılacak öğenin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Giriş bulundu ve başarıyla kaldırıldı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).

##  <a name="setat"></a>  CTypedPtrMap::SetAt

Bu üye işlevini çağırır `BASE_CLASS` **:: SetAt**.

```
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>Parametreler

*KEY*<br/>
Haritanın anahtarları türünü belirten bir şablon parametre.

*anahtar*<br/>
NewValue anahtar değerini belirtir.

*newValue*<br/>
Yeni öğe değeri nesne işaretçisi belirtir.

### <a name="remarks"></a>Açıklamalar

Daha ayrıntılı açıklamalar için bkz. [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek Topla](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr Sınıfı](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord Sınıfı](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapWordToPtr Sınıfı](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[CMapStringToPtr Sınıfı](../../mfc/reference/cmapstringtoptr-class.md)
