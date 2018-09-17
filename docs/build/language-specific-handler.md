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
ms.openlocfilehash: 678f5695523751ebc1ef3c5dba2b63154b21833c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714954"
---
# <a name="language-specific-handler"></a>Dile Özel İşleyici

UNW_FLAG_EHANDLER veya UNW_FLAG_UHANDLER bayrakları ayarlanmış her dile özel işleyici göreli adresini UNWIND_INFO öğesinde mevcuttur. Önceki bölümde açıklandığı gibi dile özel işleyici, özel durum işleyicisi için arama bir parçası olarak veya bir geriye doğru izleme bir parçası olarak adlandırılır. Aşağıdaki prototip şunları içerir:

```
typedef EXCEPTION_DISPOSITION (*PEXCEPTION_ROUTINE) (
    IN PEXCEPTION_RECORD ExceptionRecord,
    IN ULONG64 EstablisherFrame,
    IN OUT PCONTEXT ContextRecord,
    IN OUT PDISPATCHER_CONTEXT DispatcherContext
);
```

**ExceptionRecord** standart Win64 tanımını içeren bir özel durum kaydı için bir işaretçi sağlar.

**EstablisherFrame** bu işlev için sabit bir yığın ayırma taban adresidir.

**ContextRecord** noktaları (özel durum işleyicisi durumda) özel duruma neden zaman ya da geçerli özel durum bağlamı için "bırakma" bağlamında (sonlandırma işleyicisi durumda).

**DispatcherContext** bu işlev için dağıtıcı bağlamını işaret eder. Bunu aşağıdaki tanımları içerir:

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

**ControlPc** RIP bu işlev içindeki değeridir. Bir özel durum adresi ya da Denetim kurmanın işlevi sola adres budur. Bu denetim bu işlev içindeki bazı Korumalı yapı içinde olup olmadığını belirlemek için kullanılan RIP, (örneğin, __try bloğu için \__try /\__except veya \__try /\__finally).

**ImageBase** temel (yük adresi), işlev girişi kullanılan 32-bit uzaklıkları eklenmesi ve göreli adreslerini kaydetmek için bu işlevi içeren modül görüntüsüdür.

**FunctionEntry** kaynakları RUNTIME_FUNCTION işaretçi bir işlev tutarak işlev giriş ve bu işlev için bilgileri görüntü tabanlı göreli adreslerini bırakma.

**EstablisherFrame** bu işlev için sabit bir yığın ayırma taban adresidir.

**TargetIp** geriye doğru izleme devamlılık adresini belirten bir isteğe bağlı bir yönerge adresi sağlar. Bu adres yoksayılır **EstablisherFrame** belirtilmedi.

**ContextRecord** gönderme ve bırakma Sistem özel durum kodu tarafından kullanılmak üzere özel durum bağlamı işaret eder.

**LanguageHandler** çağrılan dile özgü dil işleyici rutinini işaret eder.

**HandlerData** bu işlev için dile özel işleyici veri işaret eder.

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme (x64)](../build/exception-handling-x64.md)