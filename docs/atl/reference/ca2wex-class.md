---
title: CA2WEX Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CA2WEX
- ATLCONV/ATL::CA2WEX
- ATLCONV/ATL::CA2WEX::CA2WEX
- ATLCONV/ATL::CA2WEX::m_psz
- ATLCONV/ATL::CA2WEX::m_szBuffer
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
ms.openlocfilehash: c9123e163ca828fa71fe217e46537ceb18e6f549
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319121"
---
# <a name="ca2wex-class"></a>CA2WEX Sınıfı

Bu sınıf, string dönüşüm makroları CA2TEX, CA2CTEX, CT2WEX ve CT2CWEX ve typedef CA2W tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <int t_nBufferLength = 128>
class CA2WEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğe boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CA2WEX::CA2WEX](#ca2wex)|Oluşturucu.|
|[CA2WEX::~CA2WEX](#dtor)|Yıkıcı.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CA2WEX::operatör LPWSTR](#operator_lpwstr)|Dönüşüm işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CA2WEX::m_psz](#m_psz)|Kaynak dizesini depolayan veri üyesi.|
|[CA2WEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.|

## <a name="remarks"></a>Açıklamalar

İlave işlevsellik gerekmedikçe, kodunuzda CA2TEX, CA2CTEX, CT2WEX, CT2CWEX veya CA2W kullanın.

Bu sınıf, dönüştürme sonucunu depolamak için kullanılan sabit boyutlu statik arabellek içerir. Sonuç statik arabelleğe sığmayacak kadar büyükse, sınıf **malloc**kullanarak belleği ayırır ve nesne kapsam dışına çıktığında belleği serbest eder. Bu, ATL'nin önceki sürümlerinde bulunan metin dönüştürme makrolarının aksine, bu sınıfın döngülerde kullanımının güvenli olmasını ve yığını nakışlamamasını sağlar.

Sınıf yığınüzerinde bellek ayırmaya çalışır ve başarısız olursa, `AtlThrow` E_OUTOFMEMORY bir argüman ile çağırır.

Varsayılan olarak, ATL dönüştürme sınıfları ve makrolar dönüşüm için geçerli iş parçacığının ANSI kod sayfasını kullanır. Belirli bir dönüştürme için bu davranışı geçersiz kılmak istiyorsanız, kod sayfasını sınıfın oluşturucusuna ikinci parametre olarak belirtin.

Aşağıdaki makrolar bu sınıfa dayanır:

- CA2TEX

- CA2CTEX

- CT2WEX

- CT2CWEX

Aşağıdaki typedef bu sınıfa dayanır:

- CA2W

Bu metin dönüştürme makrolarının tartışılması için [ATL ve MFC String Dönüşüm Makroları'na](string-conversion-macros.md)bakın.

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanma örneği için [ATL ve MFC String Dönüşüm Makrolarına](string-conversion-macros.md) bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlconv.h

## <a name="ca2wexca2wex"></a><a name="ca2wex"></a>CA2WEX::CA2WEX

Oluşturucu.

```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*Psz*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Dönüştürme gerçekleştirmek için kullanılan kod sayfası. Daha fazla bilgi için Windows SDK fonksiyonu [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar) için kod sayfası parametre tartışmasına bakın.

### <a name="remarks"></a>Açıklamalar

Çeviri işleminde kullanılan arabelleği ayırır.

## <a name="ca2wexca2wex"></a><a name="dtor"></a>CA2WEX::~CA2WEX

Yıkıcı.

```
~CA2WEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakın.

## <a name="ca2wexm_psz"></a><a name="m_psz"></a>CA2WEX::m_psz

Kaynak dizesini depolayan veri üyesi.

```
LPWSTR m_psz;
```

## <a name="ca2wexm_szbuffer"></a><a name="m_szbuffer"></a>CA2WEX::m_szBuffer

Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.

```
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="ca2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CA2WEX::operatör LPWSTR

Dönüşüm işleci.

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPWSTR türü olarak döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2AEX Sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX Sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CW2AEX Sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX Sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX Sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
