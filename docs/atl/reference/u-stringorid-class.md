---
title: _U_strıngorıd sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
dev_langs:
- C++
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 611fecad210b9297b6c7cd16c83dbd0c6c3e41a8
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886173"
---
# <a name="ustringorid-class"></a>_U_strıngorıd sınıfı
Bu bağımsız değişken bağdaştırıcısı sınıfı (LPCTSTRs) kaynak adları ya da kaynak kimlikleri (arayan kimliği MAKEINTRESOURCE makrosu kullanarak bir dizeye dönüştürmek gerek kalmadan bir işleve geçirilecek sınıfta) sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class _U_STRINGorID
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|Oluşturucu.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|Kaynak tanımlayıcısı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın sarmalayıcıları Windows kaynak yönetimi API'si gibi uygulamak için tasarlanmıştır [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042), [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), ve [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990) kabul işlevleri bir kaynağın adını veya kimliğini olabilecek LPCTSTR bağımsız değişken  
  
 Sınıfı iki oluşturucu aşırı yüklemeleri tanımlar: bir LPCTSTR bağımsız değişkeni kabul eder ve diğer UINT bağımsız değişkeni kabul eder. UINT bağımsız değişken MAKEINTRESOURCE makro ve sınıfın tek veri üyesi içinde depolanmış sonucu kullanarak Windows Kaynak Yönetimi işlevleri ile uyumlu bir kaynak türüne dönüştürülür [m_lpstr](#_u_stringorid__m_lpstr). LPCTSTR oluşturucusuna bağımsız değişken doğrudan dönüştürme depolanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="_u_stringorid__m_lpstr"></a>  _U_STRINGorID::m_lpstr  
 Sınıf ya da kendi oluşturucular için ortak bir LPCTSTR veri üyesi geçirilen değeri içerir.  
  
```
LPCTSTR m_lpstr;
```  
  
##  <a name="_u_stringorid___u_stringorid"></a>  _U_STRINGorID::_U_STRINGorID  
 UINT oluşturucu bağımsız değişkeni MAKEINTRESOURCE makrosu kullanılarak Windows Kaynak Yönetimi işlevleri ile uyumlu bir kaynak türü dönüştürür ve sonuç sınıfın tek veri üyesi içinde depolanır [m_lpstr](#_u_stringorid__m_lpstr).  
  
```
_U_STRINGorID(UINT nID);  
_U_STRINGorID(LPCTSTR lpString);
```  
  
### <a name="parameters"></a>Parametreler  
 *nID*  
 Bir kaynak kimliği  
  
 *lpString*  
 Bir kaynak adı.  
  
### <a name="remarks"></a>Açıklamalar  
 LPCTSTR oluşturucusuna bağımsız değişken doğrudan dönüştürme depolanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
