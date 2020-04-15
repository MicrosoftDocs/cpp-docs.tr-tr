---
title: CFixedStringT Sınıfı
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: fe096185f6f0b71ad45757cd0b75ab13c41e5f5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317822"
---
# <a name="cfixedstringt-class"></a>CFixedStringT Sınıfı

Bu sınıf sabit bir karakter arabelleği ile bir dize nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>Parametreler

*StringType*<br/>
Sabit dize nesnesi için taban sınıf `CStringT`olarak kullanılır ve herhangi bir tabanlı tür olabilir. Bazı örnekler `CString` `CStringA`şunlardır `CStringW`, , ve .

*t_nChars*<br/>
Arabellekte depolanan karakter sayısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Cfixedstringt::cfixedstringt](#cfixedstringt)|Dize nesnesinin oluşturucusu.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CFixedStringT::operatör =](#operator_eq)|Nesneye yeni bir `CFixedStringT` değer atar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, `CStringT`'ye dayalı özel bir dize sınıfı örneğidir. Benzer olmasına rağmen, iki sınıf uygulamada farklılık gösterir. Arasındaki `CFixedStringT` en büyük `CStringT` farklar şunlardır:

- İlk karakter arabelleği nesnenin bir parçası olarak ayrılır ve boyutu *t_nChars.* Bu, `CFixedString` nesnenin performans amacıyla bitişik bir bellek yığınını işgal etmesine olanak tanır. Ancak, bir `CFixedStringT` nesnenin içeriği *t_nChars*ötesinde büyürse, arabellek dinamik olarak ayrılır.

- Bir `CFixedStringT` nesnenin karakter arabelleği her zaman aynı uzunluktadır *(t_nChars).* Nesneler için `CStringT` arabellek boyutunda herhangi bir sınırlama yoktur.

- Bellek `CFixedStringT` yöneticisi, iki veya daha fazla `CFixedStringT` nesne arasında bir [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) nesnesinin paylaşılmasına izin verilmeyecek şekilde özelleştirilmiştir. `CStringT`nesnelerin bu sınırlaması yoktur.

Genel olarak dize nesneleri `CFixedStringT` için özelleştirme ve bellek yönetimi hakkında daha fazla bilgi için Bellek [Yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** cstringt.h

## <a name="cfixedstringtcfixedstringt"></a><a name="cfixedstringt"></a>Cfixedstringt::cfixedstringt

Bir `CFixedStringT` nesne inşa eder.

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
Bu `CFixedStringT` nesneye kopyalanacak null-sonlandırılan dize.

*strSrc*<br/>
Varolan `CFixedStringT` bir nesne bu `CFixedStringT` nesneye kopyalanacak.

*pStringMgr*<br/>
`CFixedStringT` Nesnenin bellek yöneticisine bir işaretçi. Için daha `IAtlStringMgr` fazla bilgi `CFixedStringT`ve bellek yönetimi için, [Bellek Yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)bakın.

### <a name="remarks"></a>Açıklamalar

Kurucular giriş verilerini yeni ayrılmış depolama alanına kopyaladığı için, bellek özel durumlarının neden olabileceğini unutmayın. Bu kuruculardan bazıları dönüşüm işlevleri olarak hareket eder.

## <a name="cfixedstringtoperator-"></a><a name="operator_eq"></a>CFixedStringT::operatör =

Varolan `CFixedStringT` bir nesneyi yeni verilerle yeniden başharfe aktarın.

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
Bu `CFixedStringT` nesneye kopyalanacak null-sonlandırılan dize.

*strSrc*<br/>
Bu `CFixedStringT` `CFixedStringT` nesneye kopyalanacak varolan bir nesne.

### <a name="remarks"></a>Açıklamalar

Atama işlecini her kullandığınızda bellek özel durumlarının oluşabileceğini, çünkü genellikle ortaya `CFixedStringT` çıkan nesneyi tutmak için yeni depolama alanı ayrılacağını unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[CStringT Sınıfı](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
