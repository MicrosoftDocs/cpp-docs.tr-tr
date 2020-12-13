---
description: 'Hakkında daha fazla bilgi edinin: _U_MENUorID sınıfı'
title: _U_MENUorID sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
ms.openlocfilehash: 4418e9db455e72643c497925c19900b41c9b9f38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138794"
---
# <a name="_u_menuorid-class"></a>_U_MENUorID sınıfı

Bu sınıf ve için sarmalayıcılar sağlar `CreateWindow` `CreateWindowEx` .

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class _U_MENUorID
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[_U_MENUorID:: _U_MENUorID](#_u_menuorid___u_menuorid)|Oluşturucu.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[_U_MENUorID:: m_hMenu](#_u_menuorid__m_hmenu)|Bir menüye yönelik bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

Bu bağımsız değişken bağdaştırıcı sınıfı, arayanın bölümünde açık bir tür dönüştürme gerektirmeden, kimlik (ler) veya menü tutamaçları (HMENUs) bir işleve geçirilmesini sağlar.

Bu sınıf, bir menü tanıtıcısı yerine bir alt pencere tanımlayıcısı (UINT) olabilecek bir HMENU bağımsız değişkenini kabul eden, özellikle [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) ve [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) işlevleri olan Windows API 'sine sarmalayıcıları uygulamak için tasarlanmıştır. Örneğin, bu sınıfın [CWindowImpl:: Create](cwindowimpl-class.md#create)için bir parametre olarak kullanılacağını görebilirsiniz.

Sınıf iki Oluşturucu aşırı yüklemesini tanımlar: One bir UINT bağımsız değişkenini kabul eder ve diğeri HMENU bağımsız değişkenini kabul eder. UINT bağımsız değişkeni, kurucudaki bir HMENU 'e ve bu durumda sınıfın tek veri üyesinde saklanan sonuç [m_hMenu](#_u_menuorid__m_hmenu). HMENU oluşturucusunun bağımsız değişkeni dönüştürme olmadan doğrudan saklanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="_u_menuoridm_hmenu"></a><a name="_u_menuorid__m_hmenu"></a> _U_MENUorID:: m_hMenu

Sınıfı, oluşturucularından birine ortak bir HMENU veri üyesi olarak geçirilen değeri barındırır.

```
HMENU m_hMenu;
```

## <a name="_u_menuorid_u_menuorid"></a><a name="_u_menuorid___u_menuorid"></a> _U_MENUorID:: _U_MENUorID

UINT bağımsız değişkeni, kurucudaki bir HMENU 'e ve bu durumda sınıfın tek veri üyesinde saklanan sonuç [m_hMenu](#_u_menuorid__m_hmenu).

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
Bir alt pencere tanımlayıcısı.

*hMenu*<br/>
Bir menü tutamacı.

### <a name="remarks"></a>Açıklamalar

HMENU oluşturucusunun bağımsız değişkeni dönüştürme olmadan doğrudan saklanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
