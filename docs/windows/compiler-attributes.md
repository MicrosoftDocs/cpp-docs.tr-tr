---
title: Derleyici öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, attributes
- attributes [C++/CLI], compiler
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c1ce698992f1f34434a476be83da6f4697f619c
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316542"
---
# <a name="compiler-attributes"></a>Derleyici Öznitelikleri

Derleyici öznitelikleri işlevleri çeşitli sağlar.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[emitidl](../windows/emitidl.md)|Tüm sonraki IDL öznitelikleri işlem görüp oluşturulan .idl dosyasında yerleştirilmiş olup olmadığını belirler.|
|[event_receiver](../windows/event-receiver.md)|Bir olay alıcısı oluşturur.|
|[event_source](../windows/event-source.md)|Olay kaynağı oluşturur.|
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[Uygulayan](../windows/implements-cpp.md)|IDL coclass'ı üyesi olmaya zorlanıp dağıtma arabirimleri belirtir.|
|[importidl](../windows/importidl.md)|Belirtilen .idl dosyası oluşturulan .idl dosyasına ekler.|
|[importlib](../windows/importlib.md)|Zaten başka bir tür kitaplığına oluşturulan tür kitaplığı için kullanılabilir derlenmiştir türleri sağlar.|
|[includelib](../windows/includelib-cpp.md)|Oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası neden olur.|
|[library_block](../windows/library-block.md)|.İdl dosyasının kitaplığı bloğu içinde bir yapısı yerleştirir.|
|[no_injected_text](../windows/no-injected-text.md)|Derleyici, özellik kullanımı sonucu olarak kod ekleme öğesinden engeller.|
|[satype](../windows/satype.md)|Veri türü belirtir `SAFEARRAY`.|
|[Sürüm](../windows/version-cpp.md)|Belirli bir sürüm arasında bir arabirim veya sınıf birden çok sürümünü tanımlar.|

## <a name="see-also"></a>Ayrıca Bkz.

[Gruplara Göre Öznitelikler](../windows/attributes-by-group.md)