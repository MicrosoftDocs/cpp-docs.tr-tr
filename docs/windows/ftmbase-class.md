---
title: FtmBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
dev_langs:
- C++
helpviewer_keywords:
- FtmBase class
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed3e9b9e66f673a3d86ded7b3d576e1203db9595
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570567"
---
# <a name="ftmbase-class"></a>FtmBase Sınıfı
Ücretsiz iş parçacıklı bir Sıralayıcı nesnesini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,   
   Microsoft::WRL::CloakedIid<IMarshal> >;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [RuntimeClass sınıfının](runtimeclass-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[FtmBase::FtmBase Oluşturucusu](../windows/ftmbase-ftmbase-constructor.md)|Yeni bir örneğini başlatır **FtmBase** sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[FtmBase::CreateGlobalInterfaceTable Metodu](../windows/ftmbase-createglobalinterfacetable-method.md)|Bir genel arabirim tablosu (GIT) oluşturur.|  
|[FtmBase::DisconnectObject Metodu](../windows/ftmbase-disconnectobject-method.md)|Zorla tüm dış bağlantılar kurulmasına nesnenin serbest bırakır. Nesnenin sunucu nesnenin uygulaması kapatmadan önce bu yöntemi çağırır.|  
|[FtmBase::GetMarshalSizeMax Metodu](../windows/ftmbase-getmarshalsizemax-method.md)|Belirtilen nesneyi belirtilen arabirim işaretçisini hazırlamak için gereken bayt sayısı üst sınırı alın.|  
|[FtmBase::GetUnmarshalClass Metodu](../windows/ftmbase-getunmarshalclass-method.md)|COM kodu için karşılık gelen proxy içeren DLL bulmak için kullandığı CLSID değerini alır. COM proxy'si başlatılmamış bir örneğini oluşturmak için bu DLL'yi yükler.|  
|[FtmBase::MarshalInterface Metodu](../windows/ftmbase-marshalinterface-method.md)|Bir akışa bir proxy nesnesi içinde bazı istemci işlemini başlatmak için gerekli verileri yazar.|  
|[FtmBase::ReleaseMarshalData Metodu](../windows/ftmbase-releasemarshaldata-method.md)|Bir sıralanmış veri paketi yok eder.|  
|[FtmBase::UnmarshalInterface Metodu](../windows/ftmbase-unmarshalinterface-method.md)|Yeni oluşturulan proxy başlatır ve proxy için bir arabirim işaretçisini döndürür.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[FtmBase::marshaller_ Veri Üyesi](../windows/ftmbase-marshaller-data-member.md)|Ücretsiz iş parçacıklı Sıralayıcı bir başvuru içerir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `FtmBase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)