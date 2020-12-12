---
description: 'Daha fazla bilgi edinin: CA2WEX Class'
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
ms.openlocfilehash: 59d0624176f01ee266b8162060b281202ef977c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165101"
---
# <a name="ca2wex-class"></a>CA2WEX Sınıfı

Bu sınıf, CA2TEX, CA2CTEX, CT2WEX ve CT2CWEX ve typedef CA2W dize dönüştürme makroları tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template <int t_nBufferLength = 128>
class CA2WEX
```

### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğin boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CA2WEX::CA2WEX](#ca2wex)|Oluşturucu.|
|[CA2WEX:: ~ CA2WEX](#dtor)|Yok edicisi.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CA2WEX:: operator LPWSTR](#operator_lpwstr)|Dönüştürme işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CA2WEX:: m_psz](#m_psz)|Kaynak dizeyi depolayan veri üyesi.|
|[CA2WEX:: m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.|

## <a name="remarks"></a>Açıklamalar

Ek işlevsellik gerekmediği takdirde kodunuzda CA2TEX, CA2CTEX, CT2WEX, CT2CWEX veya CA2W kullanın.

Bu sınıf, dönüştürmenin sonucunu depolamak için kullanılan sabit boyutlu statik bir arabellek içerir. Sonuç statik arabelleğe sığmayacak kadar büyükse, sınıf, nesne kapsam dışına geçtiğinde bellek **malloc** kullanarak belleği ayırır. Bu, metin dönüştürme makrolarının önceki ATL sürümlerinde kullanılabilir olmasını sağlar, bu sınıfın Döngülerde kullanılması güvenlidir ve yığının taşmamasını sağlar.

Sınıf, yığın üzerinde bellek ayırmayı dener ve başarısız olursa, `AtlThrow` e_outofmemory bir bağımsız değişkeniyle çağrı yapılır.

Varsayılan olarak, ATL dönüştürme sınıfları ve makroları dönüştürme için geçerli iş parçacığının ANSI kod sayfasını kullanır. Belirli bir dönüştürme için bu davranışı geçersiz kılmak istiyorsanız, sınıf için oluşturucunun ikinci parametresi olarak kod sayfasını belirtin.

Aşağıdaki makrolar bu sınıfa dayalıdır:

- CA2TEX

- CA2CTEX

- CT2WEX

- CT2CWEX

Aşağıdaki typedef bu sınıfa dayalıdır:

- CA2W

Bu metin dönüştürme makrolarıyla ilgili bir tartışma için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md).

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanmayla ilgili bir örnek için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md) .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AtlConv. h

## <a name="ca2wexca2wex"></a><a name="ca2wex"></a> CA2WEX::CA2WEX

Oluşturucu.

```cpp
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Dönüştürme işlemini gerçekleştirmek için kullanılan kod sayfası. Daha fazla ayrıntı için bkz. [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar) Windows SDK işlevi için kod sayfası parametre tartışması.

### <a name="remarks"></a>Açıklamalar

Çeviri işleminde kullanılan arabelleği ayırır.

## <a name="ca2wexca2wex"></a><a name="dtor"></a> CA2WEX:: ~ CA2WEX

Yok edicisi.

```cpp
~CA2WEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakır.

## <a name="ca2wexm_psz"></a><a name="m_psz"></a> CA2WEX:: m_psz

Kaynak dizeyi depolayan veri üyesi.

```cpp
LPWSTR m_psz;
```

## <a name="ca2wexm_szbuffer"></a><a name="m_szbuffer"></a> CA2WEX:: m_szBuffer

Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.

```cpp
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="ca2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a> CA2WEX:: operator LPWSTR

Dönüştürme işleci.

```cpp
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPWSTR türünde döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
