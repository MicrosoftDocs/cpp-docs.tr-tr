---
title: Platform::StringReference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::StringReference::StringReference
- VCCORLIB/Platform::StringReference::Data
- VCCORLIB/Platform::StringReference::Length
- VCCORLIB/Platform::StringReference::GetHSTRING
- VCCORLIB/Platform::StringReference::GetString
dev_langs:
- C++
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56f7c6b2c7699d7be96309a6ab7f060e48838475
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609669"
---
# <a name="platformstringreference-class"></a>Platform::StringReference sınıfı
Dize verileri geçirmek için kullanabileceğiniz bir iyileştirme türü `Platform::String^` giriş kopyalama işlemleri en az diğer yöntemleri için parametreleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
class StringReference  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[StringReference::StringReference](#ctor)|Örneklerini oluşturmaya yönelik iki Oluşturucu `StringReference`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[StringReference::Data](#data)|Dize verileri char16 değerler dizisi döndürür.|  
|[StringReference::Length](#length)|Dizedeki karakter sayısını döndürür.|  
|[StringReference::GetHSTRING](#gethstring)|Dize verileri, bir HSTRING döndürür.|  
|[StringReference::GetString](#getstring)|Dize verileri olarak döndüren bir `Platform::String^`.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[StringReference::operator =](#operator-assign)|Atayan bir `StringReference` yeni bir `StringReference` örneği.|  
|[StringReference::operator()](#operator-call)|Dönüştürür bir `StringReference` için bir `Platform::String^`.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Sunucu desteklenen en düşük:** Windows Server 2012  
  
 **Namespace:** platformu  
  
 **Başlık:** vccorlib.h  

## <a name="data"></a>  StringReference::Data yöntemi
Bu içeriği döndürür `StringReference` char16 değerler dizisi olarak.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
const ::default::char16 * Data() const  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Char16 UNICODE karakterler dizisi.  
  


## <a name="gethstring"></a>  StringReference::GetHSTRING yöntemi
Dize olarak içeriğini döndürür bir `__abi_HSTRING`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
__abi_HSTRING GetHSTRING() const  
  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `__abi_HSTRING` , dize verilerini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
  


## <a name="getstring"></a>  StringReference::GetString yöntemi
Dize olarak içeriğini döndürür bir `Platform::String^`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
__declspec(no_release_return) __declspec(no_refcount)  
    ::Platform::String^ GetString() const  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::String^` , dize verilerini içerir.  

## <a name="length"></a>  StringReference::Length yöntemi
Dizedeki karakter sayısını döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
unsigned int Length() const  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizedeki karakter sayısını belirten bir işaretsiz tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
  


## <a name="operator-assign"></a>  StringReference::operator = işleci
Belirtilen nesnenin geçerli atar `StringReference` nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
StringReference& operator=(const StringReference& __fstrArg);  
StringReference& operator=(const ::default::char16* __strArg);    
```  
  
### <a name="parameters"></a>Parametreler  
 `__fstrArg`  
 Adresini bir `StringReference` geçerli başlatmak için kullanılan nesne `StringReference` nesne.  
  
 `__strArg`  
 Geçerli başlatmak için kullanılan bir dizi char16 değere işaretçi `StringReference` nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Türü bir nesneye başvuru `StringReference`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çünkü `StringReference` standart bir C++ sınıfı ve başvuru sınıfı değil, içinde görünmüyor **Nesne Tarayıcısı**.  
  


## <a name="operator-call"></a>  StringReference::operator() işleci
Dönüştürür bir `StringReference` nesnesini bir `Platform::String^` nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
__declspec(no_release_return) __declspec(no_refcount)  
         operator ::Platform::String^() const  
  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Türünde bir nesne için tanıtıcı `Platform::String`.  

## <a name="ctor"></a>  StringReference::StringReference Oluşturucusu
Yeni bir örneğini başlatır `StringReference` sınıfı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
    StringReference();  
  
   StringReference(const StringReference& __fstrArg)  
  
StringReference(const ::default::char16* __strArg)  
  
StringReference(const ::default::char16* __strArg, size_t __lenArg)  
```  
  
### <a name="parameters"></a>Parametreler  
 `__fstrArg`  
 `StringReference` Verisini yeni örneği başlatmak için kullanılır.  
  
 `__strArg`  
 Yeni örnek başlatmak için kullanılan bir dizi char16 değere işaretçi.  
  
 `__lenArg`  
 İçindeki öğelerin sayısını `__strArg`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu ilk sürümü varsayılan oluşturucudur. Dosyanın ikinci sürümü yeni bir başlatır `StringReference` örneği tarafından belirtilen nesneyi bir sınıftan `__fstrArg` parametresi. Üçüncü ve dördüncü aşırı yeni bir başlatma `StringReference` char16 değerleri bir diziden örneği. char16 bir 16 bitlik UNICODE metin karakteri temsil eder.  
  


  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform::StringReference Sınıfı](../cppcx/platform-stringreference-class.md)