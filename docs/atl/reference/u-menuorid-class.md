---
title: _U_menuorıd sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
ms.openlocfilehash: 9388ca1751ee27fb25d6751c961d23e5243f2918
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495140"
---
# <a name="_u_menuorid-class"></a>_U_menuorıd sınıfı

Bu sınıf ve `CreateWindow` `CreateWindowEx`için sarmalayıcılar sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class _U_MENUorID
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[_U_MENUorID:: _U_menuorıd](#_u_menuorid___u_menuorid)|Oluşturucu.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[_U_MENUorID:: m_hMenu](#_u_menuorid__m_hmenu)|Bir menüye yönelik bir tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

Bu bağımsız değişken bağdaştırıcı sınıfı, arayanın bölümünde açık bir tür dönüştürme gerektirmeden, kimlik (ler) veya menü tutamaçları (HMENUs) bir işleve geçirilmesini sağlar.

Bu sınıf, bir menü tanıtıcısı yerine bir alt pencere tanımlayıcısı (UINT) olabilecek bir HMENU bağımsız değişkenini kabul eden, özellikle [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) ve [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) işlevleri olan Windows API 'sine sarmalayıcıları uygulamak için tasarlanmıştır. Örneğin, bu sınıfın [CWindowImpl:: Create](cwindowimpl-class.md#create)için bir parametre olarak kullanılacağını görebilirsiniz.

Sınıf iki Oluşturucu aşırı yüklemesini tanımlar: One bir UINT bağımsız değişkenini kabul eder ve diğeri HMENU bağımsız değişkenini kabul eder. UINT bağımsız değişkeni, kurucudaki bir HMENU 'e ve sınıfın tek veri üyesinde, [m_hMenu](#_u_menuorid__m_hmenu). HMENU oluşturucusunun bağımsız değişkeni dönüştürme olmadan doğrudan saklanır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID:: m_hMenu

Sınıfı, oluşturucularından birine ortak bir HMENU veri üyesi olarak geçirilen değeri barındırır.

```
HMENU m_hMenu;
```

##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID:: _U_menuorıd

UINT bağımsız değişkeni, kurucudaki bir HMENU 'e ve sınıfın tek veri üyesinde, [m_hMenu](#_u_menuorid__m_hmenu).

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
