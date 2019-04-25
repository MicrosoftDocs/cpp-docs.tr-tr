---
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
ms.openlocfilehash: 6c7649b7131e3b1620112acf89867d0731d7265d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235171"
---
# <a name="cfixedstringt-class"></a>CFixedStringT sınıfı

Bu sınıf, bir dize nesnesi ile bir sabit karakter arabelleği temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>Parametreler

*StringType*<br/>
Sabit dize nesnesi için temel sınıf olarak kullanılan ve herhangi biri `CStringT`-türüne göre. Bazı örnekler `CString`, `CStringA`, ve `CStringW`.

*t_nChars*<br/>
Arabellekteki depolanan karakterlerin sayısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFixedStringT::CFixedStringT](#cfixedstringt)|Dize nesnesi için oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFixedStringT::operator =](#operator_eq)|Yeni bir değer atar bir `CFixedStringT` nesne.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf temel bir özel dize sınıfının bir örneğidir `CStringT`. Benzer olsa da, iki sınıf uygulamasında farklı. Arasındaki temel farklar `CFixedStringT` ve `CStringT` şunlardır:

- İlk karakter arabelleği nesnesinin bir parçası ayrılır ve boyuta sahip *t_nChars*. Böylece `CFixedString` Performans nedeniyle bir bitişik bellek öbeği kaplaması için nesne. Ancak, içeriğini bir `CFixedStringT` nesne büyüdükçe ötesinde *t_nChars*, arabellek dinamik olarak ayrılır.

- Karakter arabelleği için bir `CFixedStringT` nesnesi, her zaman aynı uzunlukta ( *t_nChars*). Arabellek boyutu için ilgili bir sınırlama yoktur `CStringT` nesneleri.

- Bellek Yöneticisi için `CFixedStringT` paylaşımını şekilde özelleştirilmiş bir [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) arasında iki veya daha fazla nesne `CFixedStringT` nesneleri izin verilmiyor. `CStringT` nesneleri bu sınırlama yoktur.

Özelleştirme hakkında daha fazla bilgi için `CFixedStringT` ve dize nesneler için bellek yönetimi genel olarak, bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>Gereksinimler

**Başlık:** cstringt.h

##  <a name="cfixedstringt"></a>  CFixedStringT::CFixedStringT

Oluşturur bir `CFixedStringT` nesne.

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
Null ile sonlandırılmış bir dize bu kopyalanacak `CFixedStringT` nesne.

*strSrc*<br/>
Mevcut bir `CFixedStringT` bu kopyalanacak nesne `CFixedStringT` nesne.

*pStringMgr*<br/>
Bellek Yöneticisi için bir işaretçi `CFixedStringT` nesne. Daha fazla bilgi için `IAtlStringMgr` ve bellek yönetimi için `CFixedStringT`, bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

### <a name="remarks"></a>Açıklamalar

Oluşturucular girdi verilerini yeni ayrılan depolama alanına kopyalayın çünkü farkında olmalıdır, bellek, özel durumlar neden olabilir. Bu oluşturucular bazıları, dönüştürme işlevleri davranır.

##  <a name="operator_eq"></a>  CFixedStringT::operator =

Mevcut bir yeniden başlatır `CFixedStringT` yeni verilerle nesne.

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
Null ile sonlandırılmış bir dize bu kopyalanacak `CFixedStringT` nesne.

*strSrc*<br/>
Mevcut bir `CFixedStringT` bu kopyalanacak `CFixedStringT` nesne.

### <a name="remarks"></a>Açıklamalar

Bilmeniz gereken yeni depolama genellikle sonuç tutmak için ayrılmış olduğundan, atama işleci kullandığınızda, özel durumlar oluşabilir belleğin `CFixedStringT` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[CStringT Sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
