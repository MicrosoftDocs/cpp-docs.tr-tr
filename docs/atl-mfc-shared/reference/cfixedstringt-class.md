---
description: 'Daha fazla bilgi edinin: CFixedStringT sınıfı'
title: CFixedStringT sınıfı
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: a613716364318ced140709d2b33e9d9c4299af0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166843"
---
# <a name="cfixedstringt-class"></a>CFixedStringT sınıfı

Bu sınıf sabit karakter arabelleği olan bir String nesnesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>Parametreler

*StringType*<br/>
Sabit dize nesnesi için temel sınıf olarak kullanılır ve herhangi bir `CStringT` tabanlı tür olabilir. Bazı örnekler `CString` , `CStringA` , ve içerir `CStringW` .

*t_nChars*<br/>
Arabellekte depolanan karakterlerin sayısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFixedStringT:: CFixedStringT](#cfixedstringt)|Dize nesnesi için Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFixedStringT:: operator =](#operator_eq)|Nesnesine yeni bir değer atar `CFixedStringT` .|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, temel alınarak özel bir dize sınıfına bir örnektir `CStringT` . Benzer olsa da, iki sınıf uygulamada farklılık gösterir. Ve arasındaki önemli farklılıklar `CFixedStringT` `CStringT` şunlardır:

- İlk karakter arabelleği nesnenin bir parçası olarak ayrılır ve *t_nChars* boyut olur. Bu, `CFixedString` nesnenin performans amaçlarıyla bitişik bir bellek öbeğini kaplamasına olanak tanır. Ancak, bir `CFixedStringT` nesnenin içeriği *t_nChars* ötesinde büyüdükçe, arabellek dinamik olarak ayrılır.

- Bir nesne için karakter arabelleği `CFixedStringT` her zaman aynı uzunluktadır ( *t_nChars*). Nesneler için arabellek boyutu sınırlaması yoktur `CStringT` .

- İçin bellek Yöneticisi, `CFixedStringT` iki veya daha fazla nesne arasında bir [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) nesnesinin paylaşılmasına `CFixedStringT` izin verilmez. `CStringT` nesnelerde bu sınırlama yoktur.

`CFixedStringT`Genel olarak dize nesneleri için ve bellek yönetiminin özelleştirilmesi hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** CStringT. h

## <a name="cfixedstringtcfixedstringt"></a><a name="cfixedstringt"></a> CFixedStringT:: CFixedStringT

Bir `CFixedStringT` nesnesi oluşturur.

```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT(const StringType& strSrc);
CFixedStringT(const StringType::XCHAR* pszSrc);
explicit CFixedStringT(const StringType::YCHAR* pszSrc);
explicit CFixedStringT(const unsigned char* pszSrc);
```

### <a name="parameters"></a>Parametreler

*pszSrc*<br/>
Bu nesneye kopyalanacak null ile sonlandırılmış bir dize `CFixedStringT` .

*strSrc*<br/>
`CFixedStringT`Bu nesneye Kopyalanacak varolan bir nesne `CFixedStringT` .

*pStringMgr*<br/>
Nesnenin bellek Yöneticisi işaretçisi `CFixedStringT` . Ve için bellek yönetimi hakkında daha fazla bilgi için `IAtlStringMgr` `CFixedStringT` bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

### <a name="remarks"></a>Açıklamalar

Oluşturucular giriş verilerini yeni ayrılmış depolamaya kopyalayacağından, bellek özel durumlarının sonuç olabileceğini bilmelisiniz. Bu oluşturuculardan bazıları dönüştürme işlevleri olarak davranır.

## <a name="cfixedstringtoperator-"></a><a name="operator_eq"></a> CFixedStringT:: operator =

Varolan bir `CFixedStringT` nesneyi yeni verilerle yeniden başlatır.

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT<StringType, t_nChars>& operator=(const char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& strSrc);
```

### <a name="parameters"></a>Parametreler

*pszSrc*<br/>
Bu nesneye kopyalanacak null ile sonlandırılmış bir dize `CFixedStringT` .

*strSrc*<br/>
`CFixedStringT`Bu nesneye kopyalamak için mevcut `CFixedStringT` .

### <a name="remarks"></a>Açıklamalar

Yeni depolama genellikle sonuçta elde edilen nesneyi tutmak üzere ayrıldığından, atama işlecini her kullandığınızda bellek özel durumlarının gerçekleşebileceğini unutmayın `CFixedStringT` .

## <a name="see-also"></a>Ayrıca bkz.

[CStringT sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
