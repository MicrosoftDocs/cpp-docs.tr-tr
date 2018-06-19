---
title: WeakRef sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef class
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba7efc595be55b807cd3f044269db0debcb72407
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891704"
---
# <a name="weakref-class"></a>WeakRef Sınıfı
Temsil eden bir *zayıf başvuru* yalnızca Windows çalışma zamanı tarafından değil klasik COM kullanılabilir Zayıf başvuru olabilir ya da erişilebilir olmayabilir bir nesneyi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class WeakRef : public ComPtr<IWeakReference>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 WeakRef nesne tutan bir *güçlü başvuru*, hangi bir nesneyle ilişkilendirilen ve geçerli veya geçersiz olabilir. Güçlü bir başvuru almak için As() veya AsIID() yöntemini çağırın. Güçlü Başvuru geçerli olduğunda, ilişkili nesne erişebilir. Güçlü Başvuru olduğunda geçersiz (`nullptr`), ilişkili nesne erişilemez.  
  
 WeakRef nesne, genellikle, varlığı bir dış iş parçacığı veya uygulama tarafından denetlenen bir nesneyi temsil etmek için kullanılır. Örneğin, bir dosya nesnesine başvuru WeakRef nesnesinden oluşturun. Dosya açıkken güçlü başvurusu geçerli değil. Ancak dosyayı kapattıysanız, güçlü başvuru geçersiz hale gelir.  
  
 Davranış değişikliği olduğuna dikkat edin [olarak](../windows/weakref-as-method.md), [Asııd](../windows/weakref-asiid-method.md) ve [CopyTo](../windows/weakref-copyto-method.md) Windows 10 SDK yöntemleri. Daha önce bu yöntemlerin herhangi biriyle çağrıldıktan sonra WeakRef için iade edilemedi `nullptr` güçlü bir başvuru başarıyla, olduğu gibi aşağıdaki kodu edinilen varsa belirlemek için:  
  
```cpp  
WeakRef wr;  
strongComptrRef.AsWeak(&wr);  
  
// Now suppose that the object strongComPtrRef points to no longer exists  
// and the following code tries to get a strong ref from the weak ref:  
ComPtr<ISomeInterface> strongRef;  
HRESULT hr = wr.As(&strongRef);  
  
// This check won't work with the Windows 10 SDK version of the library.  
// Check the input pointer instead.  
if(wr == nullptr)  
{  
    wprintf(L"Couldn’t get strong ref!");  
}  
  
```  
  
 Yukarıdaki kod Windows 10 SDK kullanırken çalışmıyor (veya üstü). Bunun yerine, için geçirildi işaretçi denetleyin `nullptr`.  
  
```cpp  
if (strongRef == nullptr)  
{  
    wprintf(L"Couldn't get strong ref!");  
 }  
  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[WeakRef::WeakRef Oluşturucusu](../windows/weakref-weakref-constructor.md)|WeakRef sınıfı yeni bir örneğini başlatır.|  
|[WeakRef::~WeakRef Yıkıcısı](../windows/weakref-tilde-weakref-destructor.md)|WeakRef sınıfı, geçerli örneğini deinitializes.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[WeakRef::As Metodu](../windows/weakref-as-method.md)|Belirtilen ComPtr işaretçi parametresini belirtilen arabirimi temsil edecek şekilde ayarlar.|  
|[WeakRef::AsIID Metodu](../windows/weakref-asiid-method.md)|Belirtilen ComPtr işaretçi parametresi belirtilen arabirimi kimliğini temsil etmek için ayarlar|  
|[WeakRef::CopyTo Metodu](../windows/weakref-copyto-method.md)|Bir işaretçi bir arabirim için mevcut ise, belirtilen işaretçi değişkenine atar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[WeakRef::operator& İşleci](../windows/weakref-operator-ampersand-operator.md)|Geçerli WeakRef nesnesini temsil eden bir ComPtrRef nesnesi döndürür.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ComPtr`  
  
 `WeakRef`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)