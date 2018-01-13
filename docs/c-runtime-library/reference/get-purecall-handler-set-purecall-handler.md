---
title: _get_purecall_handler, _set_purecall_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _set_purecall_handler
- _set_purecall_handler_m
- set_purecall_handler_m
- set_purecall_handler
- stdlib/_set_purecall_handler
- stdlib/_get_purecall_handler
- _get_purecall_handler
dev_langs: C++
helpviewer_keywords:
- _set_purecall_handler function
- set_purecall_handler function
- purecall_handler
- set_purecall_handler_m function
- _purecall_handler
- _set_purecall_handler_m function
- _get_purecall_handler function
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fd6373acbea0f265b40ff3bd1c25e1229014cafa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="getpurecallhandler-setpurecallhandler"></a>_get_purecall_handler, _set_purecall_handler
İşleyiciyi alır veya hata saf sanal işlev çağrısı için ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef void (__cdecl* _purecall_handler)(void);  
  
_purecall_handler __cdecl _get_purecall_handler(void);  
  
_purecall_handler __cdecl _set_purecall_handler(   
   _purecall_handler function  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `function`  
 Saf sanal işlevi çağrıldığında çağrılacak işlev. A `_purecall_handler` işlevi geçersiz bir dönüş türüne sahip olması gerekir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Önceki `_purecall_handler`. Döndürür `nullptr` önceki hiçbir işleyici yoksa.  
  
## <a name="remarks"></a>Açıklamalar  
 `_get_purecall_handler` Ve `_set_purecall_handler` işlevleri Microsoft özgüdür ve yalnızca C++ kodu için geçerlidir.  
  
 Hiçbir uygulama içerdiğinden saf sanal işlevi çağrısı bir hatadır. Varsayılan olarak, derleyici program sonlandırır saf sanal işlevi çağrıldığında, bir hata işleyicisi işlevi çağırmak için kod oluşturur. Saf sanal işlev çağrısı, bunları hata ayıklama veya Raporlama amaçları için yakalamak için kendi hata işleyici işlevi yükleyebilirsiniz. Kendi hata işleyicisini kullanmak için olan bir işlev oluşturun `_purecall_handler` imza, ardından `_set_purecall_handler` geçerli işleyici yapma.  
  
 Olmadığı için yalnızca bir `_purecall_handler` çağırdığınızda her işlem için `_set_purecall_handler` hemen tüm iş parçacıklarının etkiler. Hiçbir iş parçacığı üzerinde son çağıran işleyici ayarlar.  
  
 Varsayılan davranış geri yüklemek için arama `_set_purecall_handler` kullanarak bir `nullptr` bağımsız değişkeni.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_get_purecall_handler`, `_set_purecall_handler`|\<cstdlib > veya \<stdlib.h >|  
  
 Uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// _set_purecall_handler.cpp  
// compile with: /W1  
#include <tchar.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
class CDerived;  
class CBase  
{  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function(void) = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase  
{  
public:  
   CDerived() : CBase(this) {};   // C4355  
   virtual void function(void) {};  
};  
  
CBase::~CBase()  
{  
   m_pDerived -> function();  
}  
  
void myPurecallHandler(void)  
{  
   printf("In _purecall_handler.");  
   exit(0);  
}  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
   _set_purecall_handler(myPurecallHandler);  
   CDerived myDerived;  
}  
```  
  
```Output  
In _purecall_handler.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata işleme](../../c-runtime-library/error-handling-crt.md)   
 [_purecall](../../c-runtime-library/reference/purecall.md)