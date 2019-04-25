---
title: Derleyici öznitelikleri (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- cl.exe compiler, attributes
- attributes [C++/CLI], compiler
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
ms.openlocfilehash: ea4d3119a640c0642664210384c297e011104411
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148308"
---
# <a name="compiler-attributes"></a>Derleyici Öznitelikleri

Derleyici öznitelikleri işlevleri çeşitli sağlar.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[emitidl](emitidl.md)|Tüm sonraki IDL öznitelikleri işlem görüp oluşturulan .idl dosyasında yerleştirilmiş olup olmadığını belirler.|
|[event_receiver](event-receiver.md)|Bir olay alıcısı oluşturur.|
|[event_source](event-source.md)|Olay kaynağı oluşturur.|
|[export](export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[implements](implements-cpp.md)|IDL coclass'ı üyesi olmaya zorlanıp dağıtma arabirimleri belirtir.|
|[importidl](importidl.md)|Belirtilen .idl dosyası oluşturulan .idl dosyasına ekler.|
|[importlib](importlib.md)|Zaten başka bir tür kitaplığına oluşturulan tür kitaplığı için kullanılabilir derlenmiştir türleri sağlar.|
|[includelib](includelib-cpp.md)|Oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası neden olur.|
|[library_block](library-block.md)|.İdl dosyasının kitaplığı bloğu içinde bir yapısı yerleştirir.|
|[no_injected_text](no-injected-text.md)|Derleyici, özellik kullanımı sonucu olarak kod ekleme öğesinden engeller.|
|[satype](satype.md)|Veri türü belirtir `SAFEARRAY`.|
|[version](version-cpp.md)|Belirli bir sürüm arasında bir arabirim veya sınıf birden çok sürümünü tanımlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Gruplara Göre Öznitelikler](attributes-by-group.md)