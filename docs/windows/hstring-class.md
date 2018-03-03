---
title: "HString sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
dev_langs:
- C++
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e8d66f134eef5f2ecb75b30fd68874418dbc49d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hstring-class"></a>HString Sınıfı
RAII desen kullanan bir HSTRING ömrünü yönetmek için bir yardımcı sınıfı.
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
class HString;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Windows çalışma zamanı dizeleri HSTRING tanıtıcıları üzerinden erişim sağlar. HString sınıfı kolaylık işlevleri ve HSTRING tanıtıcıları kullanarak basitleştirmek için işleçleri sağlar. Bu sınıf kullanım ömrünü RAII modeli aracılığıyla sahibi HSTRING işleyebilir. 
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HString::HString Oluşturucusu](../windows/hstring-hstring-constructor.md)|HString sınıfının yeni bir örneğini başlatır.|  
|[HString::~HString Yıkıcısı](../windows/hstring-tilde-hstring-destructor.md)|HString sınıfının geçerli örneği yok eder.|  
  
### <a name="members"></a>Üyeler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HString::Set Metodu](../windows/hstring-set-method.md)|Belirtilen geniş karakter dizesi veya HString parametresi için geçerli HString nesnenin değerini ayarlar.|  
|[HString::Attach Metodu](../windows/hstring-attach-method.md)|Belirtilen HString nesne geçerli HString nesnesi ile ilişkilendirir.|  
|[HString::CopyTo Metodu](../windows/hstring-copyto-method.md)|Kopya geçerli HString HSTRING nesneye nesne.|  
|[HString::Detach Metodu](../windows/hstring-detach-method.md)|Temel alınan değeri belirtilen HString nesnesinden keser.|  
|[HString::GetAddressOf Metodu](../windows/hstring-getaddressof-method.md)|Temel alınan HSTRING işlemek için bir işaretçi alır.|  
|[HString::Get Metodu](../windows/hstring-get-method.md)|Temel alınan HSTRING tanıtıcı değerini alır.|  
|[HString::Release Metodu](../windows/hstring-release-method.md)|Temel dize değeri siler ve boş bir değer için geçerli HString nesne intializes.|  
|[HString::MakeReference Metodu](../windows/hstring-makereference-method.md)|HStringReference nesneyi belirtilen string parametresinden oluşturur.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[HString::Operator= İşleci](../windows/hstring-operator-assign-operator.md)|Başka bir HString nesnenin değerini geçerli HString nesneye taşır.|  
|[HString::Operator== İşleci](../windows/hstring-operator-equality-operator.md)|İki parametre eşit olup olmadığını gösterir.|  
|[HString::Operator!= İşleci](../windows/hstring-operator-inequality-operator.md)|İki parametre eşit olup olmadığını gösterir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `HString`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)