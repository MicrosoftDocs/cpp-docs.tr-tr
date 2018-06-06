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
ms.openlocfilehash: 38f30c497fc8640b1f88f4ffb3fc6f14bed55a3e
ms.sourcegitcommit: e3b4ef19b534a2ed48bb9091e5197a6e536f16c1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34814358"
---
# <a name="ftmbase-class"></a>FtmBase Sınıfı
Ücretsiz iş parçacıklı Sıralayıcı nesneyi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,   
   Microsoft::WRL::CloakedIid<IMarshal> >;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [RuntimeClass sınıfı](runtimeclass-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[FtmBase::FtmBase Oluşturucusu](../windows/ftmbase-ftmbase-constructor.md)|FtmBase sınıfı yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[FtmBase::CreateGlobalInterfaceTable Metodu](../windows/ftmbase-createglobalinterfacetable-method.md)|Genel arabirim tablosu (GIT) oluşturur.|  
|[FtmBase::DisconnectObject Metodu](../windows/ftmbase-disconnectobject-method.md)|Zorla nesneye tüm dış bağlantıları serbest bırakır. Nesnenin sunucu nesnenin uyarlamasını kapatmadan önce bu yöntemi çağırır.|  
|[FtmBase::GetMarshalSizeMax Metodu](../windows/ftmbase-getmarshalsizemax-method.md)|Belirtilen nesne üzerindeki belirtilen arabirim işaretçisi hazırlamak için gereken bayt sayısı üst sınırı öğrenin.|  
|[FtmBase::GetUnmarshalClass Metodu](../windows/ftmbase-getunmarshalclass-method.md)|COM için karşılık gelen proxy kodu içeren DLL bulmak için kullandığı CLSID alır. COM proxy başlatılmamış bir örneğini oluşturmak için bu DLL yükler.|  
|[FtmBase::MarshalInterface Metodu](../windows/ftmbase-marshalinterface-method.md)|Bazı istemci işleminde proxy nesneyi başlatmak için gerekli olan veriler bir akışa yazar.|  
|[FtmBase::ReleaseMarshalData Metodu](../windows/ftmbase-releasemarshaldata-method.md)|Bir sıralanmış veri paketi yok eder.|  
|[FtmBase::UnmarshalInterface Metodu](../windows/ftmbase-unmarshalinterface-method.md)|Yeni oluşturulan bir proxy başlatır ve proxy için bir arabirim işaretçisi döndürür.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[FtmBase::marshaller_ Veri Üyesi](../windows/ftmbase-marshaller-data-member.md)|Ücretsiz iş parçacıklı Sıralayıcı başvuru tutar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `FtmBase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)