---
title: CFixedStringT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9f48ffb9cad787159a40a58d85e6bff5dacc475
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808257"
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
|[CFixedStringT::operator =](#eq)|Yeni bir değer atar bir `CFixedStringT` nesne.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf temel bir özel dize sınıfının bir örneğidir `CStringT`. Oldukça benzer olsa da, iki sınıf uygulamasında farklı. Arasındaki temel farklar `CFixedStringT` ve `CStringT` şunlardır:

- İlk karakter arabelleği nesnesinin bir parçası ayrılır ve boyuta sahip *t_nChars*. Böylece `CFixedString` Performans nedeniyle bir bitişik bellek öbeği kaplaması için nesne. Ancak, içeriğini bir `CFixedStringT` nesne büyüdükçe ötesinde *t_nChars*, arabellek dinamik olarak ayrılır.

- Karakter arabelleği için bir `CFixedStringT` nesnesi, her zaman aynı uzunlukta ( *t_nChars*). Arabellek boyutu için ilgili bir sınırlama yoktur `CStringT` nesneleri.

- Bellek Yöneticisi için `CFixedStringT` paylaşımını şekilde özelleştirilmiş bir [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) arasında iki veya daha fazla nesne `CFixedStringT` objectsis izin verilmiyor. `CStringT` nesneleri bu sınırlama yoktur.

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
CFixedStringT(const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT(const StringType& str);
CFixedStringT(const StringType::XCHAR* psz);
explicit CFixedStringT(const StringType::YCHAR* psz);
explicit CFixedStringT(const unsigned char* psz);
```

### <a name="parameters"></a>Parametreler

*psz*<br/>
Null ile sonlandırılmış bir dize bu kopyalanacak `CFixedStringT` nesne.

*str*<br/>
Mevcut bir `CFixedStringT` bu kopyalanacak nesne `CFixedStringT` nesne.

*pStringMgr*<br/>
Bellek Yöneticisi için bir işaretçi `CFixedStringT` nesne. Daha fazla bilgi için `IAtlStringMgr` ve bellek yönetimi için `CFixedStringT`, bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

### <a name="remarks"></a>Açıklamalar

Oluşturucular girdi verilerini yeni ayrılan depolama alanına kopyalayın çünkü farkında olmalıdır, bellek, özel durumlar neden olabilir. Bu oluşturucular bazıları dönüştürme işlevleri davranan unutmayın.

##  <a name="operator__eq"></a>  CFixedStringT::operator =

Mevcut bir yeniden başlatır `CFixedStringT` yeni verilerle nesne.

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT<StringType, t_nChars>& operator=(const char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* psz);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Null ile sonlandırılmış bir dize bu kopyalanacak `CFixedStringT` nesne.

*psz*<br/>
Mevcut bir `CFixedStringT` bu kopyalanacak `CFixedStringT` nesne.

### <a name="remarks"></a>Açıklamalar

Bilmeniz gereken yeni depolama genellikle sonuç tutmak için ayrılmış olduğundan, atama işleci kullandığınızda, özel durumlar oluşabilir belleğin `CFixedStringT` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[CStringT Sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)

