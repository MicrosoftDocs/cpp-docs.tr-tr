---
description: 'Daha fazla bilgi edinin: CW2AEX Class'
title: CW2AEX sınıfı
ms.date: 11/04/2016
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
ms.openlocfilehash: dfb654c43f2549cc1cfe58be064b2e6b9621fc69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140289"
---
# <a name="cw2aex-class"></a>CW2AEX sınıfı

Bu sınıf, CT2AEX, CW2TEX, CW2CTEX ve CT2CAEX ve typedef CW2A dize dönüştürme makroları tarafından kullanılır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<int t_nBufferLength = 128>
class CW2AEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işleminde kullanılan arabelleğin boyutu. Varsayılan uzunluk 128 bayttır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CW2AEX::CW2AEX](#cw2aex)|Oluşturucu.|
|[CW2AEX:: ~ CW2AEX](#dtor)|Yok edicisi.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CW2AEX:: operator LPSTR](#operator_lpstr)|Dönüştürme işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CW2AEX:: m_psz](#m_psz)|Kaynak dizeyi depolayan veri üyesi.|
|[CW2AEX:: m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.|

## <a name="remarks"></a>Açıklamalar

Ek işlevsellik gerekmediği takdirde kodunuzda CT2AEX, CW2TEX, CW2CTEX, CT2CAEX veya CW2A kullanın.

Bu sınıf, dönüştürmenin sonucunu depolamak için kullanılan sabit boyutlu statik bir arabellek içerir. Sonuç statik arabelleğe sığmayacak kadar büyükse, sınıf, nesne kapsam dışına geçtiğinde bellek **malloc** kullanarak belleği ayırır. Bu, metin dönüştürme makrolarının önceki ATL sürümlerinde kullanılabilir olmasını sağlar, bu sınıfın Döngülerde kullanılması güvenlidir ve yığının taşmamasını sağlar.

Sınıf, yığın üzerinde bellek ayırmayı dener ve başarısız olursa, `AtlThrow` e_outofmemory bir bağımsız değişkeniyle çağrı yapılır.

Varsayılan olarak, ATL dönüştürme sınıfları ve makroları dönüştürme için geçerli iş parçacığının ANSI kod sayfasını kullanır. Belirli bir dönüştürme için bu davranışı geçersiz kılmak istiyorsanız, sınıf için oluşturucunun ikinci parametresi olarak kod sayfasını belirtin.

Aşağıdaki makrolar bu sınıfa dayalıdır:

- CT2AEX

- CW2TEX

- CW2CTEX

- CT2CAEX

Aşağıdaki typedef bu sınıfa dayalıdır:

- CW2A

Bu metin dönüştürme makrolarıyla ilgili bir tartışma için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md).

## <a name="example"></a>Örnek

Bu dize dönüştürme makrolarını kullanmayla ilgili bir örnek için bkz. [ATL ve MFC dize dönüştürme makroları](string-conversion-macros.md) .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AtlConv. h

## <a name="cw2aexcw2aex"></a><a name="cw2aex"></a> CW2AEX::CW2AEX

Oluşturucu.

```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2AEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*PSZ*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Dönüştürme işlemini gerçekleştirmek için kullanılan kod sayfası. Daha fazla ayrıntı için bkz. [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar) Windows SDK işlevi için kod sayfası parametre tartışması.

### <a name="remarks"></a>Açıklamalar

Çeviri işleminde kullanılan arabelleği ayırır.

## <a name="cw2aexcw2aex"></a><a name="dtor"></a> CW2AEX:: ~ CW2AEX

Yok edicisi.

```
~CW2AEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan arabelleği serbest bırakır.

## <a name="cw2aexm_psz"></a><a name="m_psz"></a> CW2AEX:: m_psz

Kaynak dizeyi depolayan veri üyesi.

```
LPSTR m_psz;
```

## <a name="cw2aexm_szbuffer"></a><a name="m_szbuffer"></a> CW2AEX:: m_szBuffer

Dönüştürülmüş dizeyi depolamak için kullanılan statik arabellek.

```
char m_szBuffer[t_nBufferLength];
```

## <a name="cw2aexoperator-lpstr"></a><a name="operator_lpstr"></a> CW2AEX:: operator LPSTR

Dönüştürme işleci.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesini LPSTR türünde döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)<br/>
[CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
