---
title: "_U_STRINGorID sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ebc1b8f65f2a0841baf09b5c95528f571f97ce38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ustringorid-class"></a>_U_STRINGorID sınıfı
Bu bağımsız değişken bağdaştırıcı sınıfı ya da kaynak adları verir ( `LPCTSTR`s) veya kaynak kimlikleri ( **UINT**s) kullanarak bir dize kimliği dönüştürmek arayan gerek kalmadan bir işleve iletilecek **MAKEINTRESOURCE** makrosu.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
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
 Bu sınıf Windows kaynak yönetimi API için sarmalayıcıları gibi uygulamak için tasarlanmıştır [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042), [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), ve [LoadMenu](http://msdn.microsoft.com/library/windows/desktop/ms647990) kabul işlevleri bir `LPCTSTR` bir kaynağın adını veya kimliğini olabilir bağımsız değişken  
  
 Sınıfın iki Oluşturucusu aşırı tanımlar: bir kabul bir `LPCTSTR` bağımsız değişkeni ve diğer kabul eden bir **UINT** bağımsız değişkeni. **UINT** bağımsız değişkeni kullanarak Windows Kaynak Yönetimi işlevleri ile uyumlu bir kaynak türü için dönüştürülür **MAKEINTRESOURCE** makrosu ve sınıfın tek veri üyesi depolanmış sonucu [m_lpstr](#_u_stringorid__m_lpstr). Bağımsız değişkeni `LPCTSTR` Oluşturucusu doğrudan dönüştürme olmadan depolanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="_u_stringorid__m_lpstr"></a>_U_STRINGorID::m_lpstr  
 Sınıf ya da oluşturucular genel olarak geçirilen değeri tutan `LPCTSTR` veri üyesi.  
  
```
LPCTSTR m_lpstr;
```  
  
##  <a name="_u_stringorid___u_stringorid"></a>_U_STRINGorID::_U_STRINGorID  
 **UINT** oluşturucu bağımsız değişkeni kullanarak Windows Kaynak Yönetimi işlevleri ile uyumlu bir kaynak türü dönüştürür **MAKEINTRESOURCE** makrosu ve sonucu sınıfın tek depolanır veri üyesi [m_lpstr](#_u_stringorid__m_lpstr).  
  
```
_U_STRINGorID(UINT nID);  
_U_STRINGorID(LPCTSTR lpString);
```  
  
### <a name="parameters"></a>Parametreler  
 `nID`  
 Bir kaynak kimliği  
  
 `lpString`  
 Bir kaynak adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişkeni `LPCTSTR` Oluşturucusu doğrudan dönüştürme olmadan depolanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
