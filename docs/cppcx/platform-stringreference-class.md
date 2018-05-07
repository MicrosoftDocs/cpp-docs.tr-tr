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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 646a09dd46e123f0bc7eadc178e3741367e908ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="platformstringreference-class"></a>Platform::StringReference sınıfı
Dize verilerini geçirmek için kullanabileceğiniz bir en iyi duruma getirme türü `Platform::String^` giriş parametreleri kopyalama işlemleri en az diğer yöntemleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
class StringReference  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[StringReference::StringReference](#ctor)|Örneklerini oluşturmaya yönelik iki oluşturucular `StringReference`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[StringReference::Data](#data)|Dize verilerini char16 değerleri dizisi döndürür.|  
|[StringReference::Length](#length)|Dizesindeki karakterlerin sayısını döndürür.|  
|[StringReference::GetHSTRING](#gethstring)|Dize verilerini bir HSTRING döndürür.|  
|[StringReference::GetString](#getstring)|Dize olarak döndürür bir `Platform::String^`.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[StringReference::operator =](#operator-assign)|Atayan bir `StringReference` yeni bir `StringReference` örneği.|  
|[StringReference::operator()](#operator-call)|Dönüştüren bir `StringReference` için bir `Platform::String^`.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Başlık:** vccorlib.h  

## <a name="data"></a>  StringReference::Data yöntemi
Bu içeriğini döndürür `StringReference` char16 değerleri dizisi olarak.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
const ::default::char16 * Data() const  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Char16 UNICODE metin karakter dizisi.  
  


## <a name="gethstring"></a>  StringReference::GetHSTRING yöntemi
Dize olarak içeriğini döndürür bir `__abi_HSTRING`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
__abi_HSTRING GetHSTRING() const  
  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `__abi_HSTRING` dize verilerini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
  


## <a name="getstring"></a>  StringReference::GetString yöntemi
Dize olarak içeriğini döndürür bir `Platform::String^`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
__declspec(no_release_return) __declspec(no_refcount)  
    ::Platform::String^ GetString() const  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::String^` dize verilerini içerir.  

## <a name="length"></a>  StringReference::Length yöntemi
Dizesindeki karakterlerin sayısını döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
unsigned int Length() const  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizesindeki karakterlerin sayısını belirtir imzalanmamış tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
  


## <a name="operator-assign"></a>  StringReference::operator = işleci
Belirtilen nesne geçerli atar `StringReference` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
StringReference& operator=(const StringReference& __fstrArg);  
StringReference& operator=(const ::default::char16* __strArg);    
```  
  
### <a name="parameters"></a>Parametreler  
 `__fstrArg`  
 Adresini bir `StringReference` geçerli başlatmak için kullanılan nesne `StringReference` nesne.  
  
 `__strArg`  
 İşaretçi geçerli başlatmak için kullanılan bir dizi char16 değerlerin `StringReference` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru türünde bir nesne `StringReference`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çünkü `StringReference` standart C++ sınıfı ve ref sınıfı, içinde görünmez **Nesne Tarayıcısı**.  
  


## <a name="operator-call"></a>  StringReference::operator() işleci
Dönüştüren bir `StringReference` nesnesine bir `Platform::String^` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
__declspec(no_release_return) __declspec(no_refcount)  
         operator ::Platform::String^() const  
  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir nesne türü için bir tanıtıcı `Platform::String`.  

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
 Yeni örnek başlatmak için kullanılan bir dizi char16 değerlerin işaretçi.  
  
 `__lenArg`  
 Öğe sayısı `__strArg`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk bu oluşturucuyu varsayılan oluşturucu sürümüdür. İkinci sürümü yeni bir başlatır `StringReference` örneği tarafından belirtilen nesne sınıfından `__fstrArg` parametresi. Üçüncü ve dördüncü aşırı yeni bir başlatma `StringReference` bir dizi örneği char16 değerleri. char16 16 bit UNICODE metin karakteri temsil eder.  
  


  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform::StringReference Sınıfı](../cppcx/platform-stringreference-class.md)