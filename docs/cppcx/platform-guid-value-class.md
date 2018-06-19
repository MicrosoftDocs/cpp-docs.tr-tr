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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c295138d6239ce516b4f322fb5fc479e2235a6be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089457"
---
# <a name="platformguid-value-class"></a>Platform::Guid değer sınıfı
Temsil eden bir [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) Windows çalışma zamanı tür sistemi türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public value struct Guid  
```  
  
### <a name="members"></a>Üyeler  
 GUID'ye sahip GetHashCode(), Equals() ve ToString() yöntemleri türetilen [Platform::Object sınıfı](../cppcx/platform-object-class.md), ve GetTypeCode() yöntemi türetilmiş [Platform::Type sınıfı](../cppcx/platform-type-class.md). GUID, aşağıdaki üyeleri de vardır.  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[GUID](#ctor)|GUID yapısı yeni bir örneğini başlatır.|  
|[operator==](#operator-equality)|Eşittir işleci.|  
|[operator!=](#operator-not-equal)|Eşit değil işleci.|  
|[operator()](#operator-call)|Bir GUID bir GUID olarak dönüştürür.|  
  
### <a name="remarks"></a>Açıklamalar  
 Windows işlevini kullanarak yeni bir Platform::Guid oluşturmak nasıl bir örnek için [Cocreateguid'de](http://msdn.microsoft.com/library/windows/desktop/ms688568\(v=vs.85\).aspx), bkz: [WinRT bileşen: bir GUID oluşturmak nasıl?](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  

 
## <a name="ctor"></a> Guid::guid oluşturucular
GUID yapı yeni bir örneğini başlatır.  
  
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
 GUID ilk 4 bayt.  
  
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
Örtük olarak dönüştürür bir [GUID yapısı](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx)bir Platform::Guid için GUID.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Platform::Guid operator()  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 GUID yapı.  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)