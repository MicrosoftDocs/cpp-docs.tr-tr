---
title: "CInternetException sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
dev_langs: C++
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8caa275af4469d45672125677d960b71212fe3de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cinternetexception-class"></a>CInternetException sınıfı
Bir Internet işlemle ilişkili bir özel durumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CInternetException : public CException  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInternetException::CInternetException](#cinternetexception)|Oluşturan bir `CInternetException` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInternetException::m_dwContext](#m_dwcontext)|Özel duruma neden işlemle ilişkili içerik değeri.|  
|[CInternetException::m_dwError](#m_dwerror)|Özel duruma neden hata.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CInternetException` Sınıfı, iki genel veri üyelerini içerir: bir özel durum ile ilişkili hata kodunu içerir ve diğer hata ile ilişkili Internet uygulama Bağlam tanıtıcısı tutar.  
  
 Internet uygulamaları için bağlam tanımlayıcıları hakkında daha fazla bilgi için bkz: [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="cinternetexception"></a>CInternetException::CInternetException  
 Bu üye işlevi aldığında çağrılan bir `CInternetException` nesnesi oluşturulur.  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwError`  
 Özel duruma neden hata.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir CInternetException throw için MFC genel işlevini çağırın [Afxthrowınternetexception](internet-url-parsing-globals.md#afxthrowinternetexception).  
  
##  <a name="m_dwcontext"></a>CInternetException::m_dwContext  
 İlgili Internet işlemle ilişkili içerik değeri.  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlam tanıtıcısı başlangıçta belirtilen [CInternetSession](../../mfc/reference/cinternetsession-class.md) ve MFC'ye tarafından geçirilen [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- ve [CInternetFile](../../mfc/reference/cinternetfile-class.md)-türetilmiş sınıfları. Bu varsayılanı geçersiz kılabilir ve herhangi bir Ata `dwContext` parametresi seçtiğiniz bir değer. `dwContext`verilen nesnenin herhangi bir işlem ile ilişkilidir. `dwContext`işlem durumu bilgileri tarafından döndürülen tanımlayan [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
##  <a name="m_dwerror"></a>CInternetException::m_dwError  
 Özel duruma neden hata.  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu hata değerini bir sistem olabilir hata kodu, WINERROR içinde bulunamadı. H veya WİNINET hatası değerinden. H.  
  
 Win32 hata kodlarına listesi için bkz: [hata kodları](http://msdn.microsoft.com/library/windows/desktop/ms681381). Internet özel hata iletileri listesi için bkz. Her iki Windows SDK'ın konulardır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CException sınıfı](../../mfc/reference/cexception-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CException Sınıfı](../../mfc/reference/cexception-class.md)
