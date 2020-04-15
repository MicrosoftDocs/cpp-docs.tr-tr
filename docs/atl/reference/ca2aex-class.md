---
title: CA2AEX Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CA2AEX
- ATLCONV/ATL::CA2AEX
- ATLCONV/ATL::CA2AEX::CA2AEX
- ATLCONV/ATL::CA2AEX::m_psz
- ATLCONV/ATL::CA2AEX::m_szBuffer
helpviewer_keywords:
- CA2AEX class
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
ms.openlocfilehash: 4f8b9f91e9bc499523fe3484bc76325e2efb8140
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319176"
---
# <a name="ca2aex-class"></a>CA2AEX Sınıfı

Bu sınıf dize dönüştürme makroları CA2TEX ve CT2AEX ve typedef CA2A tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <int t_nBufferLength = 128>
class CA2AEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğe boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CA2AEX::CA2AEX](#ca2aex)|Oluşturucu.|
|[CA2AEX::~CA2AEX](#dtor)|Yıkıcı.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CA2AEX::operatör LPSTR](#operator_lpstr)|Dönüşüm işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CA2AEX::m_psz](#m_psz)|Kaynak dizesini depolayan veri üyesi.|
|[CA2AEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.|

## <a name="remarks"></a>Açıklamalar

İlave işlevsellik gerekmedikçe, kendi kodunuzda CA2TEX, CT2AEX veya CA2A kullanın.

Bu sınıf, dönüştürme sonucunu depolamak için kullanılan sabit boyutlu statik arabellek içerir. Sonuç statik arabelleğe sığmayacak kadar büyükse, sınıf **malloc**kullanarak belleği ayırır ve nesne kapsam dışına çıktığında belleği serbest eder. Bu, ATL'nin önceki sürümlerinde bulunan metin dönüştürme makrolarının aksine, bu sınıfın döngülerde kullanımının güvenli olmasını ve yığını nakışlamamasını sağlar.

Sınıf yığınüzerinde bellek ayırmaya çalışır ve başarısız olursa, `AtlThrow` E_OUTOFMEMORY bir argüman ile çağırır.

Varsayılan olarak, ATL dönüştürme sınıfları ve makrolar dönüşüm için geçerli iş parçacığının ANSI kod sayfasını kullanır.

Aşağıdaki makrolar bu sınıfa dayanır:

- CA2TEX

- CT2AEX

Aşağıdaki typedef bu sınıfa dayanır:

- CA2A

Bu metin dönüştürme makrolarının tartışılması için [ATL ve MFC String Dönüşüm Makroları'na](string-conversion-macros.md)bakın.

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanma örneği için [ATL ve MFC String Dönüşüm Makrolarına](string-conversion-macros.md) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlconv.h

## <a name="ca2aexca2aex"></a><a name="ca2aex"></a>CA2AEX::CA2AEX

Oluşturucu.

```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*Psz*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Bu sınıfta kullanılmayan.

### <a name="remarks"></a>Açıklamalar

Çeviri için gerekli arabelleği oluşturur.

## <a name="ca2aexca2aex"></a><a name="dtor"></a>CA2AEX::~CA2AEX

Yıkıcı.

```
~CA2AEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakın.

## <a name="ca2aexm_psz"></a><a name="m_psz"></a>CA2AEX::m_psz

Kaynak dizesini depolayan veri üyesi.

```
LPSTR m_psz;
```

## <a name="ca2aexm_szbuffer"></a><a name="m_szbuffer"></a>CA2AEX::m_szBuffer

Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.

```
char m_szBuffer[ t_nBufferLength];
```

## <a name="ca2aexoperator-lpstr"></a><a name="operator_lpstr"></a>CA2AEX::operatör LPSTR

Dönüşüm işleci.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPSTR türü olarak döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2CAEX Sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX Sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX Sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX Sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
