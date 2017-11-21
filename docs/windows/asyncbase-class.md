---
title: "AsyncBase sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase
dev_langs: C++
helpviewer_keywords: AsyncBase class
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ad32c1ed42a2a991ba9ed9bd550330bc460834cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbase-class"></a>AsyncBase Sınıfı
Windows çalışma zamanı zaman uyumsuz durum makinesinin uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
template <  
   typename TComplete,  
   typename TProgress = Details::Nil,  
   AsyncResultType resultType = SingleResult  
>  
class AsyncBase : public AsyncBase< TComplete, Details::Nil, resultType >;  
  
template <  
   typename TComplete,  
   AsyncResultType resultType  
>  
class AsyncBase< TComplete, Details::Nil, resultType > : public Microsoft::WRL::Implements< IAsyncInfo >;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TComplete`  
 Zaman uyumsuz bir işlem tamamlandıktan sonra çağrılan bir olay işleyicisi.  
  
 `TProgress`  
 Çalıştırma zaman uyumsuz bir işlem işlemi geçerli ilerlemesini bildirdiğinde çağrılan bir olay işleyicisi.  
  
 `resultType`  
 Aşağıdakilerden birini [AsyncResultType](../windows/asyncresulttype-enumeration.md) numaralandırma değerleri. Varsayılan olarak, SingleResult.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AsyncBase::AsyncBase Oluşturucusu](../windows/asyncbase-asyncbase-constructor.md)|AsyncBase sınıfı örneği başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AsyncBase::Cancel yöntemi](../windows/asyncbase-cancel-method.md)|Zaman uyumsuz bir işlem iptal eder.|  
|[AsyncBase::Close yöntemi](../windows/asyncbase-close-method.md)|Zaman uyumsuz işlemi kapatır.|  
|[AsyncBase::FireCompletion yöntemi](../windows/asyncbase-firecompletion-method.md)|Tamamlama olay işleyiciyi çağırır veya iç ilerleme temsilci sıfırlar.|  
|[AsyncBase::FireProgress yöntemi](../windows/asyncbase-fireprogress-method.md)|Geçerli ilerleme olay işleyiciyi çağırır.|  
|[AsyncBase::get_ErrorCode yöntemi](../windows/asyncbase-get-errorcode-method.md)|Geçerli zaman uyumsuz işlemi için hata kodunu alır.|  
|[Asyncbase::get_ıd yöntemi](../windows/asyncbase-get-id-method.md)|Zaman uyumsuz işlemi işleyicisini alır.|  
|[AsyncBase::get_Status yöntemi](../windows/asyncbase-get-status-method.md)|Zaman uyumsuz işlemin durumunu gösteren bir değer alır.|  
|[AsyncBase::GetOnComplete yöntemi](../windows/asyncbase-getoncomplete-method.md)|Geçerli tamamlama olay işleyicisinin adresi belirtilen değişkenine kopyalar.|  
|[AsyncBase::GetOnProgress yöntemi](../windows/asyncbase-getonprogress-method.md)|Geçerli ilerleme olay işleyicisinin adresi belirtilen değişkenine kopyalar.|  
|[Asyncbase::put_ıd yöntemi](../windows/asyncbase-put-id-method.md)|Zaman uyumsuz işlem tanıtıcısı ayarlar.|  
|[AsyncBase::PutOnComplete yöntemi](../windows/asyncbase-putoncomplete-method.md)|Tamamlama olay işleyicisi adresini belirtilen değere ayarlar.|  
|[AsyncBase::PutOnProgress yöntemi](../windows/asyncbase-putonprogress-method.md)|Devam eden olay işleyicisi adresini belirtilen değere ayarlar.|  
|[AsyncBase::Start yöntemi](../windows/asyncbase-start-method.md)|Zaman uyumsuz işlemi başlatır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AsyncBase::CheckValidStateForDelegateCall yöntemi](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|Temsilci özellikleri geçerli zaman uyumsuz durumunda değiştirilebilir olup olmadığını sınar.|  
|[AsyncBase::CheckValidStateForResultsCall yöntemi](../windows/asyncbase-checkvalidstateforresultscall-method.md)|Zaman uyumsuz bir işlem sonuçlarını geçerli zaman uyumsuz durumunda toplanabilir olup olmadığını sınar.|  
|[AsyncBase::ContinueAsyncOperation yöntemi](../windows/asyncbase-continueasyncoperation-method.md)|Zaman uyumsuz işlem işleme devam etmesi gerektiğini veya durdurmak belirler.|  
|[AsyncBase::CurrentStatus yöntemi](../windows/asyncbase-currentstatus-method.md)|Geçerli zaman uyumsuz işlemin durumunu alır.|  
|[AsyncBase::ErrorCode yöntemi](../windows/asyncbase-errorcode-method.md)|Geçerli zaman uyumsuz işlemi için hata kodunu alır.|  
|[AsyncBase::OnCancel yöntemi](../windows/asyncbase-oncancel-method.md)|Türetilen bir sınıfta geçersiz kılındığında, zaman uyumsuz bir işlem iptal eder.|  
|[AsyncBase::OnClose yöntemi](../windows/asyncbase-onclose-method.md)|Türetilen bir sınıfta geçersiz kılındığında, zaman uyumsuz bir işlem kapatır.|  
|[AsyncBase::OnStart yöntemi](../windows/asyncbase-onstart-method.md)|Türetilen bir sınıfta geçersiz kılındığında, zaman uyumsuz bir işlem başlatır.|  
|[AsyncBase::TryTransitionToCompleted yöntemi](../windows/asyncbase-trytransitiontocompleted-method.md)|Geçerli zaman uyumsuz işlemi tamamlanıp tamamlanmadığını gösterir.|  
|[AsyncBase::TryTransitionToError yöntemi](../windows/asyncbase-trytransitiontoerror-method.md)|Belirtilen hata kodu iç hata durumu değişiklik olup olmadığını gösterir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `AsyncBase`  
  
 `AsyncBase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)