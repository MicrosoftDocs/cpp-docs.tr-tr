---
title: _U_STRINGorID Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
ms.openlocfilehash: 4e46ceec077b8daf8ef2a76110d2fc19dd39ae26
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325817"
---
# <a name="_u_stringorid-class"></a>_U_STRINGorID Sınıfı

Bu bağımsız değişken bağdaştırıcı sı, arayan kişinin MAKEINTRESOURCE makrosu kullanarak kimliği bir dize dönüştürmesine gerek kalmadan kaynak adlarının (LPCTSTR'ler) veya kaynak kimliklerinin (UINTs) bir işleve geçirilmesini sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class _U_STRINGorID
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|Oluşturucu.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[_U_STRINGorID:m_lpstr](#_u_stringorid__m_lpstr)|Kaynak tanımlayıcısı.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, [findresource,](/windows/win32/api/winbase/nf-winbase-findresourcea) [LoadIcon](/windows/win32/api/winuser/nf-winuser-loadiconw)ve [LoadMenu](/windows/win32/api/winuser/nf-winuser-loadmenuw) işlevleri gibi Windows kaynak yönetimi API'sine paketleyiciler uygulamak için tasarlanmıştır ve bu da kaynağın adı veya kimliği olabilecek bir LPCTSTR bağımsız değişkenini kabul eder.

Sınıf iki oluşturucu aşırı yükleri tanımlar: biri LPCTSTR bağımsız değişkenini, diğeri ise UINT bağımsız değişkenini kabul eder. UINT bağımsız değişkeni, MAKEINTRESOURCE makrosu ve sınıfın tek veri üyesi [m_lpstr](#_u_stringorid__m_lpstr)depolanan sonuç kullanılarak Windows kaynak yönetimi işlevleriyle uyumlu bir kaynak türüne dönüştürülür. LPCTSTR oluşturucuya gelen bağımsız değişken, dönüşüm olmadan doğrudan depolanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="_u_stringoridm_lpstr"></a><a name="_u_stringorid__m_lpstr"></a>_U_STRINGorID:m_lpstr

Sınıf, ortak LPCTSTR veri üyesi olarak oluşturucularından herhangi biri için geçirilen değeri tutar.

```
LPCTSTR m_lpstr;
```

## <a name="_u_stringorid_u_stringorid"></a><a name="_u_stringorid___u_stringorid"></a>_U_STRINGorID::_U_STRINGorID

UINT oluşturucu, bağımsız değişkenini MAKEINTRESOURCE makrosu kullanarak Windows kaynak yönetimi işlevleriyle uyumlu bir kaynak türüne dönüştürür ve sonuç sınıfın tek veri üyesi nde depolanır, [m_lpstr.](#_u_stringorid__m_lpstr)

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
Kaynak kimliği.

*lpString*<br/>
Kaynak adı.

### <a name="remarks"></a>Açıklamalar

LPCTSTR oluşturucuya gelen bağımsız değişken, dönüşüm olmadan doğrudan depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
