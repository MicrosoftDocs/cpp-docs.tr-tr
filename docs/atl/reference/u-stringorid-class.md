---
description: 'Hakkında daha fazla bilgi edinin: _U_STRINGorID sınıfı'
title: _U_STRINGorID sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
ms.openlocfilehash: bbbf3d32e86d035344ba8d3dcd60c4ebe66d9c3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138768"
---
# <a name="_u_stringorid-class"></a>_U_STRINGorID sınıfı

Bu bağımsız değişken bağdaştırıcı sınıfı, kaynak adlarının (LPCTSTRs) veya kaynak kimliklerinin (litre), çağıranın KIMLIĞI MAKEINTRESOURCE makrosunu kullanarak bir dizeye dönüştürmek zorunda kalmadan bir işleve geçirilmesini sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class _U_STRINGorID
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[_U_STRINGorID:: _U_STRINGorID](#_u_stringorid___u_stringorid)|Oluşturucu.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[_U_STRINGorID:: m_lpstr](#_u_stringorid__m_lpstr)|Kaynak tanımlayıcısı.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir kaynağın adı ya da KIMLIĞI olabilen bir LPCTSTR bağımsız değişkenini kabul eden [FindResource](/windows/win32/api/winbase/nf-winbase-findresourcea), [LoadIcon](/windows/win32/api/winuser/nf-winuser-loadiconw)ve [LoadMenu](/windows/win32/api/winuser/nf-winuser-loadmenuw) işlevleri gibi Windows kaynak yönetimi API 'sine sarmalayıcıları uygulamak için tasarlanmıştır.

Sınıf iki Oluşturucu aşırı yüklemesini tanımlar: One bir LPCTSTR bağımsız değişkenini kabul eder ve diğeri bir UINT bağımsız değişkenini kabul eder. UINT bağımsız değişkeni, MAKEINTRESOURCE makrosunu ve sınıfın tek veri üyesinde saklanan sonucu kullanan Windows kaynak yönetimi işlevleri ile uyumlu bir kaynak türüne dönüştürülür. [m_lpstr](#_u_stringorid__m_lpstr). LPCTSTR oluşturucusunun bağımsız değişkeni dönüştürme olmadan doğrudan saklanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="_u_stringoridm_lpstr"></a><a name="_u_stringorid__m_lpstr"></a> _U_STRINGorID:: m_lpstr

Sınıfı, oluşturucularından birine ortak bir LPCTSTR veri üyesi olarak geçirilen değeri barındırır.

```
LPCTSTR m_lpstr;
```

## <a name="_u_stringorid_u_stringorid"></a><a name="_u_stringorid___u_stringorid"></a> _U_STRINGorID:: _U_STRINGorID

UINT Oluşturucusu, bağımsız değişkenini MAKEINTRESOURCE makrosunu kullanarak Windows kaynak yönetimi işlevleri ile uyumlu bir kaynak türüne dönüştürür ve sonuç sınıfın tek veri üyesinde saklanır, [m_lpstr](#_u_stringorid__m_lpstr).

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Kaynak KIMLIĞI.

*Lpstrıng*<br/>
Bir kaynak adı.

### <a name="remarks"></a>Açıklamalar

LPCTSTR oluşturucusunun bağımsız değişkeni dönüştürme olmadan doğrudan saklanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
