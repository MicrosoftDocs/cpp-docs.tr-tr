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
ms.openlocfilehash: d02d00e3c56fc253e8f89eec9815e01d60c6e2aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196990"
---
# <a name="umenuorid-class"></a>_U_menuorıd sınıfı

Bu sınıfın sarmalayıcıları için sağladığı `CreateWindow` ve `CreateWindowEx`.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class _U_MENUorID
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|Oluşturucu.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Bir menüye tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

Bu bağımsız değişken bağdaştırıcı sınıfı yoluna arayan kimlikleri (sınıfta) ya da menü tutamaçlarını (açık bir tür dönüştürme gerektirmeden bir işleve geçirilecek HMENUs) sağlar.

Bu sınıfın sarmalayıcıları Windows API uygulamak için tasarlanmıştır özellikle [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) ve [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) İşlevler, ikisi için de bir alt pencere olabilecek HMENU bağımsız değişken kabul edin tanımlayıcı (UINT) yerine bir menü tanıtıcısı. Örneğin, bir parametre olarak kullanımı bu sınıfta görebilirsiniz [CWindowImpl::Create](cwindowimpl-class.md#create).

Sınıfı iki oluşturucu aşırı yüklemeleri tanımlar: bir UINT bağımsız değişkeni kabul eder ve diğer HMENU bağımsız değişken kabul eder. UINT bağımsız değişken yalnızca bir HMENU oluşturucusu ve sınıfın tek veri üyesi içinde depolanmış sonuç türüne dönüştürülür [m_hMenu](#_u_menuorid__m_hmenu). HMENU oluşturucusuna bağımsız değişken doğrudan dönüştürme depolanır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="_u_menuorid__m_hmenu"></a>  _U_MENUorID::m_hMenu

Sınıf ya da kendi oluşturucular için ortak bir HMENU veri üyesi geçirilen değeri içerir.

```
HMENU m_hMenu;
```

##  <a name="_u_menuorid___u_menuorid"></a>  _U_MENUorID::_U_MENUorID

UINT bağımsız değişken yalnızca bir HMENU oluşturucusu ve sınıfın tek veri üyesi içinde depolanmış sonuç türüne dönüştürülür [m_hMenu](#_u_menuorid__m_hmenu).

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
Bir alt pencere tanımlayıcısı.

*hMenu*<br/>
Bir menü tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

HMENU oluşturucusuna bağımsız değişken doğrudan dönüştürme depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
