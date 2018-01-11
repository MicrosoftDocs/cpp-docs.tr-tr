---
title: "Platform::IntPtr değer sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/PlatformIntPtr::IntPtr
- VCCORLIB/PlatformIntPtr::op_explicit Operator
- VCCORLIB/PlatformIntPtr::ToInt32
dev_langs: C++
helpviewer_keywords: Platform::IntPtr Struct
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 787e8aaa0dc46a651fc4d0ac8b16d9521aebd010
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformintptr-value-class"></a>Platform::IntPtr değer sınıfı
İmzalı bir işaretçi veya tanıtıcısı ve özelliği temsil eden platforma özgü boyutudur (32 bit veya 64 bit).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public value struct IntPtr  
```  
  
### <a name="members"></a>Üyeler  
 IntPtr aşağıdaki üyeleri vardır:  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[IntPtr::IntPtr](#ctor)|IntPtr yeni bir örneğini başlatır.|  
|[IntPtr::op_Explicit işleci](#op-explicit)|Belirtilen parametre IntPtr veya bir işaretçi bir IntPtr değerine dönüştürür.|  
|[IntPtr::ToInt32](#toint32)|Geçerli IntPtr 32-bit tamsayıya dönüştürür.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  

## <a name="ctor"></a> IntPtr::IntPtr Oluşturucusu
Belirtilen değerle IntPtr yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );  
```  
  
### <a name="parameters"></a>Parametreler  
 value  
 Bir 64-bit tanıtıcı veya işaretçi veya 64-bitlik bir değer veya 64-bit değerine dönüştürülebilir 32 bitlik bir değer için bir işaretçi.  
  


## <a name="op-explicit"></a> IntPtr::op_Explicit işleci
Belirtilen parametre IntPtr veya bir işaretçi bir IntPtr değerine dönüştürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
### <a name="parameters"></a>Parametreler  
 Değer1  
 Bir işaretçi bir tanıtıcı veya IntPtr.  
  
 Value2  
 Bir IntPtr dönüştürülebilir bir 32 bit tam sayı.  
  
 Değer3  
 IntPtr.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birinci ve ikinci işleçleri IntPtr döndür. Üçüncü işleci geçerli IntPtr tarafından temsil edilen değer için bir işaretçi döndürür.  
  


## <a name="toint32"></a> IntPtr::ToInt32 yöntemi
Geçerli IntPtr değer 32-bit tamsayıya dönüştürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
int32 IntPtr::ToInt32();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir 32 bit tamsayı.  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)