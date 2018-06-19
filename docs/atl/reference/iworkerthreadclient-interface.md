---
title: IWorkerThreadClient arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
dev_langs:
- C++
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8336edb07d02bbbcd5775eaf3ef8fe0f735d3adb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359823"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient arabirimi
`IWorkerThreadClient` istemcileri tarafından uygulanan arabirimi [CWorkerThread](../../atl/reference/cworkerthread-class.md) sınıfı.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
__interface IWorkerThreadClient
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CloseHandle](#closehandle)|Bu nesneyle ilişkili tanıtıcı kapatmak için bu yöntemi uygulaması.|  
|[Yürütme](#execute)|Bu nesneyle ilişkili tanıtıcı işaret hale zaman kod yürütmek için bu yöntemi uygulaması.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir çalışan iş parçacığı işaret olma işlenecek yanıt yürütmek için gereken kodu varsa, bu arabirimi uygular.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle  
 Bu nesneyle ilişkili tanıtıcı kapatmak için bu yöntemi uygulaması.  
  
```
HRESULT CloseHandle(HANDLE  hHandle);
```  
  
### <a name="parameters"></a>Parametreler  
 *hHandle*  
 Kapatılması işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı veya başarısızlık HRESULT hata S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yönteme geçirilen tanıtıcı çağrısı ile bu nesne ile daha önce ilişkili [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod basit bir uyarlamasını gösterir `IWorkerThreadClient::CloseHandle`.  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 Bu nesneyle ilişkili tanıtıcı işaret hale zaman kod yürütmek için bu yöntemi uygulaması.  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwParam`  
 Kullanıcı parametresi.  
  
 `hObject`  
 İşaret hale işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarı veya başarısızlık HRESULT hata S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tanıtıcı ve DWORD/işaretçi bu yönteme geçirilen bir çağrı tarafından bu nesne ile daha önce ilişkili [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod basit bir uyarlamasını gösterir `IWorkerThreadClient::Execute`.  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfları](../../atl/reference/atl-classes.md)   
 [CWorkerThread Sınıfı](../../atl/reference/cworkerthread-class.md)
