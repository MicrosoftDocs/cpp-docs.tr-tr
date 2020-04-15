---
title: CW2WEX Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
ms.openlocfilehash: b116775a595f9fb3612d46e19526cf1396f85002
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330344"
---
# <a name="cw2wex-class"></a>CW2WEX Sınıfı

Bu sınıf dize dönüştürme makroları CW2TEX ve CT2WEX ve typedef CW2W tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <int t_nBufferLength = 128>
class CW2WEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğe boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CW2WEX::CW2WEX](#cw2wex)|Oluşturucu.|
|[CW2WEX::~CW2WEX](#dtor)|Yıkıcı.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CW2WEX::operatör LPWSTR](#operator_lpwstr)|Dönüşüm işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CW2WEX::m_psz](#m_psz)|Kaynak dizesini depolayan veri üyesi.|
|[CW2WEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.|

## <a name="remarks"></a>Açıklamalar

İlave işlevsellik gerekmedikçe, kodunuzda CW2TEX, CT2WEX veya CW2W kullanın.

Bu sınıf, dönüştürme sonucunu depolamak için kullanılan sabit boyutlu statik arabellek içerir. Sonuç statik arabelleğe sığmayacak kadar büyükse, sınıf **malloc**kullanarak belleği ayırır ve nesne kapsam dışına çıktığında belleği serbest eder. Bu, ATL'nin önceki sürümlerinde bulunan metin dönüştürme makrolarının aksine, bu sınıfın döngülerde kullanımının güvenli olmasını ve yığını nakışlamamasını sağlar.

Sınıf yığınüzerinde bellek ayırmaya çalışır ve başarısız olursa, `AtlThrow` E_OUTOFMEMORY bir argüman ile çağırır.

Varsayılan olarak, ATL dönüştürme sınıfları ve makrolar dönüşüm için geçerli iş parçacığının ANSI kod sayfasını kullanır.

Aşağıdaki makrolar bu sınıfa dayanır:

- CW2TEX

- CT2WEX

Aşağıdaki typedef bu sınıfa dayanır:

- CW2W

Bu metin dönüştürme makrolarının tartışılması için [ATL ve MFC String Dönüşüm Makroları'na](string-conversion-macros.md)bakın.

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanma örneği için [ATL ve MFC String Dönüşüm Makrolarına](string-conversion-macros.md) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlconv.h

## <a name="cw2wexcw2wex"></a><a name="cw2wex"></a>CW2WEX::CW2WEX

Oluşturucu.

```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*Psz*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Kod sayfası. Bu sınıfta kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Çeviri için gerekli arabelleği oluşturur.

## <a name="cw2wexcw2wex"></a><a name="dtor"></a>CW2WEX::~CW2WEX

Yıkıcı...

```
~CW2WEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakın.

## <a name="cw2wexm_psz"></a><a name="m_psz"></a>CW2WEX::m_psz

Kaynak dizesini depolayan veri üyesi.

```
LPWSTR m_psz;
```

## <a name="cw2wexm_szbuffer"></a><a name="m_szbuffer"></a>CW2WEX::m_szBuffer

Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.

```
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="cw2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CW2WEX::operatör LPWSTR

Döküm operatörü.

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPWSTR türü olarak döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2AEX Sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX Sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX Sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX Sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
