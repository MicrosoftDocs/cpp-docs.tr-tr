---
description: 'Daha fazla bilgi edinin: CW2WEX Class'
title: CW2WEX sınıfı
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
ms.openlocfilehash: 87dbcefe37a54270b021ee1446ba5ccba2ef8313
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140250"
---
# <a name="cw2wex-class"></a>CW2WEX sınıfı

Bu sınıf, CW2TEX ve CT2WEX dize dönüştürme makroları ve typedef CW2W tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <int t_nBufferLength = 128>
class CW2WEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğin boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CW2WEX::CW2WEX](#cw2wex)|Oluşturucu.|
|[CW2WEX:: ~ CW2WEX](#dtor)|Yok edicisi.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CW2WEX:: operator LPWSTR](#operator_lpwstr)|Dönüştürme işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CW2WEX:: m_psz](#m_psz)|Kaynak dizeyi depolayan veri üyesi.|
|[CW2WEX:: m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.|

## <a name="remarks"></a>Açıklamalar

Ek işlevsellik gerekmediği takdirde kodunuzda CW2TEX, CT2WEX veya CW2W kullanın.

Bu sınıf, dönüştürmenin sonucunu depolamak için kullanılan sabit boyutlu statik bir arabellek içerir. Sonuç statik arabelleğe sığmayacak kadar büyükse, sınıf, nesne kapsam dışına geçtiğinde bellek **malloc** kullanarak belleği ayırır. Bu, metin dönüştürme makrolarının önceki ATL sürümlerinde kullanılabilir olmasını sağlar, bu sınıfın Döngülerde kullanılması güvenlidir ve yığının taşmamasını sağlar.

Sınıf, yığın üzerinde bellek ayırmayı dener ve başarısız olursa, `AtlThrow` e_outofmemory bir bağımsız değişkeniyle çağrı yapılır.

Varsayılan olarak, ATL dönüştürme sınıfları ve makroları dönüştürme için geçerli iş parçacığının ANSI kod sayfasını kullanır.

Aşağıdaki makrolar bu sınıfa dayalıdır:

- CW2TEX

- CT2WEX

Aşağıdaki typedef bu sınıfa dayalıdır:

- CW2W

Bu metin dönüştürme makrolarıyla ilgili bir tartışma için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md).

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanmayla ilgili bir örnek için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md) .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AtlConv. h

## <a name="cw2wexcw2wex"></a><a name="cw2wex"></a> CW2WEX::CW2WEX

Oluşturucu.

```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Kod sayfası. Bu sınıfta kullanılmıyor.

### <a name="remarks"></a>Açıklamalar

Çeviri için gereken arabelleği oluşturur.

## <a name="cw2wexcw2wex"></a><a name="dtor"></a> CW2WEX:: ~ CW2WEX

Yok edici..

```
~CW2WEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakır.

## <a name="cw2wexm_psz"></a><a name="m_psz"></a> CW2WEX:: m_psz

Kaynak dizeyi depolayan veri üyesi.

```
LPWSTR m_psz;
```

## <a name="cw2wexm_szbuffer"></a><a name="m_szbuffer"></a> CW2WEX:: m_szBuffer

Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.

```
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="cw2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a> CW2WEX:: operator LPWSTR

Cast işleci.

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPWSTR türünde döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
