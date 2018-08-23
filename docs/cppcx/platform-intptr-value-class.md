---
title: Platform::IntPtr değer sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformIntPtr::IntPtr
- VCCORLIB/PlatformIntPtr::op_explicit Operator
- VCCORLIB/PlatformIntPtr::ToInt32
dev_langs:
- C++
helpviewer_keywords:
- Platform::IntPtr Struct
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a97d77f0b84366c83f09f6a6c72afe1bbb25dc6d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612135"
---
# <a name="platformintptr-value-class"></a>Platform::IntPtr değer sınıfı
İmzalı bir işaretçi veya tanıtıcı ve ayarlanmış gösteren boyutudur, platforma özgü (32 bit veya 64-bit).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public value struct IntPtr  
```  
  
### <a name="members"></a>Üyeler  
 IntPtr aşağıdaki üyeleri içerir:  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[IntPtr::IntPtr](#ctor)|IntPtr yeni bir örneğini başlatır.|  
|[IntPtr::op_Explicit işleci](#op-explicit)|Belirtilen parametre bir IntPtr ya da bir işaretçi bir IntPtr değerine dönüştürür.|  
|[IntPtr::ToInt32](#toint32)|Geçerli IntPtr bir 32-bit tamsayıya dönüştürür.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Sunucu desteklenen en düşük:** Windows Server 2012  
  
 **Namespace:** platformu  
  
 **Meta veri:** platform.winmd  

## <a name="ctor"> </a> IntPtr::IntPtr Oluşturucusu
Belirtilen değerle bir IntPtr yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );  
```  
  
### <a name="parameters"></a>Parametreler  
 value  
 Bir 64-bit tanıtıcı veya işaretçi veya 64-bit bir değer ya da bir 64-bit değere dönüştürülebilir 32-bit bir değer için bir işaretçi.  
  


## <a name="op-explicit"> </a> IntPtr::op_Explicit işleci
Belirtilen parametre bir IntPtr ya da bir işaretçi bir IntPtr değerine dönüştürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
### <a name="parameters"></a>Parametreler  
 Değer1  
 Tanıtıcı ya da IntPtr yönelik işaretçi.  
  
 Value2  
 İçin bir IntPtr dönüştürülebilir bir 32 bit tamsayı.  
  
 Değeri3  
 Bir IntPtr.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birinci ve ikinci işleçleri bir IntPtr döndürür. Üçüncü işleci bir işaretçi geçerli IntPtr tarafından temsil edilen değeri döndürür.  
  


## <a name="toint32"> </a> IntPtr::ToInt32 yöntemi
Geçerli IntPtr değer 32-bit tamsayıya dönüştürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
int32 IntPtr::ToInt32();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir 32 bit tamsayı.  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)