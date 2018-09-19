---
title: CW2CWEX sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b45945a0f91570d78d8c1e365fd70240c2385b3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116808"
---
# <a name="cw2cwex-class"></a>CW2CWEX sınıfı

Bu sınıf, dize dönüşüm makroları CW2CTEX ve CT2CWEX ve typedef CW2W tarafından kullanılır.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<int t_nBufferLength = 128>
class CW2CWEX
```

#### <a name="parameters"></a>Parametreler

*t_nBufferLength*<br/>
Çeviri işlemde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CW2CWEX::CW2CWEX](#cw2cwex)|Oluşturucu.|
|[CW2CWEX:: ~ CW2CWEX](#dtor)|Yıkıcı.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CW2CWEX::operator LPCWSTR](#operator_lpcwstr)|Dönüştürme işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CW2CWEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|

## <a name="remarks"></a>Açıklamalar

Ek işlevler gerekmiyorsa CW2CTEX, CT2CWEX veya CW2W kodunuzda kullanın.

Bu sınıf Döngülerde kullanmak güvenlidir ve stack overflow olmaz. Varsayılan olarak, geçerli iş parçacığının ANSI kod sayfasına dönüştürme için ATL dönüştürme sınıfları ve makroları kullanın.

Aşağıdaki makroları bu sınıfa bağlıdır:

- CW2CTEX

- CT2CWEX

Aşağıdaki tür tanımı bu sınıfa bağlıdır:

- CW2W

Bu metin dönüşüm makroları bir tartışma için bkz [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md).

## <a name="example"></a>Örnek

Bkz: [ATL ve MFC dize dönüşüm makroları](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlconv.h

##  <a name="cw2cwex"></a>  CW2CWEX::CW2CWEX

Oluşturucu.

```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2CWEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Parametreler

*psz*<br/>
Dönüştürülecek metin dizesi.

*nCodePage*<br/>
Kod sayfası. Bu sınıfta kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Çeviri işlemde kullanılan arabellek ayırır.

##  <a name="dtor"></a>  CW2CWEX:: ~ CW2CWEX

Yıkıcı.

```
~CW2CWEX() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılmış ara belleğini serbest bırakır.

##  <a name="m_psz"></a>  CW2CWEX::m_psz

Kaynak dizesi depolar veri üyesi.

```
LPCWSTR m_psz;
```

##  <a name="operator_lpcwstr"></a>  CW2CWEX::operator LPCWSTR

Dönüştürme işleci.

```
operator LPCWSTR() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Metin dizesi LPCWSTR türü olarak döndürür.

## <a name="see-also"></a>Ayrıca Bkz.

[CA2AEX Sınıfı](../../atl/reference/ca2aex-class.md)<br/>
[CA2CAEX Sınıfı](../../atl/reference/ca2caex-class.md)<br/>
[CA2WEX Sınıfı](../../atl/reference/ca2wex-class.md)<br/>
[CW2AEX Sınıfı](../../atl/reference/cw2aex-class.md)<br/>
[CW2WEX Sınıfı](../../atl/reference/cw2wex-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
