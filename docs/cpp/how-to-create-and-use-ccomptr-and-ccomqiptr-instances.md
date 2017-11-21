---
title: "Nasıl yapılır: oluşturma ve kullanma CComPtr ve CComQIPtr örnekleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b0356cfb-12cc-4ee8-b988-8311ed1ab5e0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 27843430e1615f42dd7c5404f4eb8ba5bbb1aa39
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-create-and-use-ccomptr-and-ccomqiptr-instances"></a>Nasıl yapılır: CComPtr ve CComQIPtr Örnekleri Oluşturma ve Kullanma
Klasik Windows programlama kitaplıkları genellikle olarak COM nesneleri (veya daha hassas bir şekilde COM sunucuları) uygulanır. Çoğu Windows işletim sistemi bileşenleri COM sunucuları olarak uygulanır ve bu formda kitaplıkları pek çok katkıda bulunanlar sağlar. COM temel kavramları hakkında daha fazla bilgi için bkz [Bileşen Nesne Modeli (COM)](http://msdn.microsoft.com/en-us/3578ca42-a4b6-44b3-ad5b-aeb5fa61f3f4).  
  
 Bileşen Nesne Modeli (COM) nesne örneği, arabirim işaretçisi başvuru çağrıları kullanarak sayım gerçekleştirir bir COM akıllı işaretçi depolamak `AddRef` ve `Release` yıkıcı içinde. Etkin Şablon kitaplığı (ATL) veya Microsoft Foundation Class Kitaplığı (MFC) kullanıyorsanız, daha sonra kullanmak `CComPtr` akıllı işaretçi. ATL veya MFC kullanmıyorsanız, daha sonra kullanmak `_com_ptr_t`. Eşdeğer hiçbir COM olduğundan `std::unique_ptr`, bu akıllı işaretçiler tek sahip ve birden çok sahibi senaryoları için kullanın. Her ikisi de `CComPtr` ve `ComQIPtr` destek rvalue başvuru işlemleri taşıma.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir `CComPtr` bir COM nesnesinin örneği ve arabirimlerinden işaretçiler edinmek için. Dikkat `CComPtr::CoCreateInstance` üye işlevini, aynı ada sahip Win32 işlevi yerine COM nesnesi oluşturmak için kullanılır.  
  
 [!code-cpp[COM_smart_pointers#01](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_1.cpp)]  
  
 `CComPtr`ve kendi akrabaları ATL parçası olan ve atlcomcli.h tanımlanır. `_com_ptr_t`içinde comip.h bildirildi. Özelleştirmeleri, derleyici oluşturur `_com_ptr_t` tür kitaplıkları için sarmalayıcı sınıflar oluşturduğunda.  
  
## <a name="example"></a>Örnek  
 ATL de sağlar `CComQIPtr`, ek bir arabirim almak için bir COM nesnesinin sorgulamak için daha basit bir sözdizimi içeriyor. Ancak, öneririz `CComPtr` , her şeyi mevcut olduğundan `CComQIPtr` yapabilirsiniz ve anlam olarak ham COM arabirimi işaretçileri ile daha tutarlı. Kullanırsanız, bir `CComPtr` için bir arabirimi sorgulamak için yeni arabirim işaretçisi bir out parametresi yerleştirilir. Çağrı başarısız olursa, tipik bir COM Düzen olduğu HRESULT döndürülür. İle `CComQIPtr`işaretçi dönüş değerdir ve çağrısı başarısız olursa, iç HRESULT dönüş değeri erişilemez. Aşağıdaki iki satırları göster nasıl de mekanizmaları işleme hatası `CComPtr` ve `CComQIPtr` farklılık gösterir.  
  
 [!code-cpp[COM_smart_pointers#02](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_2.cpp)]  
  
## <a name="example"></a>Örnek  
 `CComPtr`COM Otomasyon bileşenleri işaretçiler depolamak ve geç bağlama kullanarak arabirimde yöntemleri çağırma sağlar IDispatch için bir uzmanlık sağlar. `CComDispatchDriver`typedef için olan `CComQIPtr<IDispatch, &IIDIDispatch>`, örtük olarak dönüştürülebilir olduğu `CComPtr<IDispatch>`. Bu üç adlarının herhangi biri kodda göründüğünde, bu nedenle, eşdeğerdir `CComPtr<IDispatch>`. Aşağıdaki örnek Microsoft Word nesne modelini gösteren bir işaretçi kullanarak edinmeyi gösteren bir `CComPtr<IDispatch>`.  
  
 [!code-cpp[COM_smart_pointers#03](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md)