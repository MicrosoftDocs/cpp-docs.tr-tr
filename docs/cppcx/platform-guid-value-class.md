---
title: Platform::guid değer sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
dev_langs:
- C++
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d971d4cce8dc3a9d01a666bc8e0e6333f85260c8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201380"
---
# <a name="platformguid-value-class"></a>Platform::Guid değer sınıfı
Temsil eden bir [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) Windows çalışma zamanı tür sisteminde türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public value struct Guid  
```  
  
### <a name="members"></a>Üyeler  
 GetHashCode(), üzerine yaz GUID değeri vardır ve ToString() yöntemleri türetilen [Platform::Object sınıfı](../cppcx/platform-object-class.md), ve GetTypeCode() yöntemi türetilmiş [Platform::Type sınıfı](../cppcx/platform-type-class.md). GUID, aşağıdaki üyeleri de içerir.  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[GUID](#ctor)|GUID struct'ın yeni bir örneğini başlatır.|  
|[operator==](#operator-equality)|Eşittir işleci.|  
|[operator!=](#operator-not-equal)|Eşit değil işleci.|  
|[operator()](#operator-call)|Bir GUID GUID olarak dönüştürür.|  
  
### <a name="remarks"></a>Açıklamalar  
 Windows işlevi kullanarak yeni bir Platform::Guid oluşturmak nasıl bir örnek için [Cocreateguid'de](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateguid), bakın [WinRT bileşeni: bir GUID oluşturun nasıl?](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Sunucu desteklenen en düşük:** Windows Server 2012  
  
 **Namespace:** platformu  
  
 **Meta veri:** platform.winmd  

 
## <a name="ctor"></a> Guid::guid oluşturucular
Bir GUID yapı yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        unsigned char d,   
        unsigned char e,   
        unsigned char f,   
        unsigned char g,   
        unsigned char h,   
        unsigned char i,   
        unsigned char j,   
        unsigned char k  );  
  
    Guid(GUID m);  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        Array<unsigned char>^ n );  
```  
  
### <a name="parameters"></a>Parametreler  
 `a`  
 GUID ilk 4 baytı.  
  
 `b`  
 GUID'nin sonraki 2 baytı.  
  
 `c`  
 GUID'nin sonraki 2 baytı.  
  
 `d`  
 GUID'nin sonraki baytı.  
  
 `e`  
 GUID'nin sonraki baytı.  
  
 `f`  
 GUID'nin sonraki baytı.  
  
 `g`  
 GUID'nin sonraki baytı.  
  
 `h`  
 GUID'nin sonraki baytı.  
  
 `i`  
 GUID'nin sonraki baytı.  
  
 `j`  
 GUID'nin sonraki baytı.  
  
 `k`  
 GUID'nin sonraki baytı.  
  
 `m`  
 Tanımlanan bir GUID.  
  
 `n`  
 GUID kalan 8 bayt.  
  

## <a name="operator-equality"></a> Guid::operator == işleci
İki GUID karşılaştırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Platform::Guid::operator==  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İki GUID eşitse TRUE.

## <a name="operator-inequality"></a> Guid::operator! = işleci
İki GUID karşılaştırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Platform::Guid::operator!=  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İki GUID eşit değilse true.



## <a name="operator-call"></a> Guid::operator() işleci
Örtük olarak dönüştürür bir [GUID yapısı](https://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx)bir Platform::Guid GUID.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Platform::Guid operator()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir GUID yapı.  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)