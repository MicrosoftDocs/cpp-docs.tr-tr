---
title: Dile özel işleyici | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6503e0cd-2d3a-4330-a925-8bed8c27c2be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6cbfbe6a9b98828a63fb4a092717bfab583e9a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="language-specific-handler"></a>Dile Özel İşleyici
UNW_FLAG_EHANDLER veya UNW_FLAG_UHANDLER bayrakları ayarlamak her dile özel işleyici göreli adresini UNWIND_INFO öğesinde mevcuttur. Önceki bölümde açıklandığı gibi dile özel işleyici araması bir özel durum işleyici için bir parçası olarak veya bırakmayla bir parçası olarak adlandırılır. Aşağıdaki prototipe sahiptir:  
  
```  
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (  
    IN PEXCEPTION_RECORD ExceptionRecord,  
    IN ULONG64 EstablisherFrame,  
    IN OUT PCONTEXT ContextRecord,  
    IN OUT PDISPATCHER_CONTEXT DispatcherContext  
);  
```  
  
 **ExceptionRecord** standart Win64 tanımını içeren bir özel durum kaydı için bir işaretçi sağlar.  
  
 **EstablisherFrame** bu işlev için sabit yığın ayırma tabanı adresidir.  
  
 **ContextRecord** özel durumu (özel durum işleyici durumda) yükseltildi saatteki veya geçerli özel durum bağlamı noktalarına "bırakma" bağlamını (sonlandırma işleyicisi durumda).  
  
 **DispatcherContext** bu işlev için dağıtıcı bağlamını işaret eder. Aşağıdaki tanımı vardır:  
  
```  
typedef struct _DISPATCHER_CONTEXT {  
    ULONG64 ControlPc;  
    ULONG64 ImageBase;  
    PRUNTIME_FUNCTION FunctionEntry;  
    ULONG64 EstablisherFrame;  
    ULONG64 TargetIp;  
    PCONTEXT ContextRecord;  
    PEXCEPTION_ROUTINE LanguageHandler;  
    PVOID HandlerData;  
} DISPATCHER_CONTEXT, *PDISPATCHER_CONTEXT;  
```  
  
 **ControlPc** RIP bu işlev içinde değerdir. Bu, bir özel durum adresi ya da Denetim kurucu işlevden sola adresi değil. Bu denetim bu işlev içinde bazı Korumalı yapı içinde olup olmadığını belirlemek için kullanılan RIP olur (örneğin, bir yapıda bloğu için \__try /\__except veya \__try /\__finally).  
  
 **ImageBase** temel (yük adresi) işlevi girişte kullanılan 32-bit uzaklıkları eklenmesi ve göreli adresleri kaydetmek için bilgilerindeki bu işlevi içeren modülü görüntüdür.  
  
 **FunctionEntry** kaynakları RUNTIME_FUNCTION işaretçi bir işlev tutarak işlev giriş ve bu işlev için bilgi görüntü tabanlı göreli adresleri bırakma.  
  
 **EstablisherFrame** bu işlev için sabit yığın ayırma tabanı adresidir.  
  
 **TargetIp** bırakma devamlılık adresini belirten bir isteğe bağlı talimat adresi sağlar. Bu adres yoksayılır **EstablisherFrame** belirtilmedi.  
  
 **ContextRecord** gönderme/bırakma Sistem özel durum kodu tarafından kullanılmak üzere özel durum bağlamı işaret eder.  
  
 **LanguageHandler** çağrılan dile özgü dil işleyicisi yordamına işaret eder.  
  
 **HandlerData** bu işlev için dile özel işleyici verileri işaret eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme (x64)](../build/exception-handling-x64.md)