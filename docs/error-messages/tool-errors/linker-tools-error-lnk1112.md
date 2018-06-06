---
title: Bağlayıcı araçları hatası LNK1112 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1112
dev_langs:
- C++
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79ca2afc7270a69c443447d1b294ee7ec8bbe5a7
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705003"
---
# <a name="linker-tools-error-lnk1112"></a>Bağlayıcı Araçları Hatası LNK1112

> Modül makine türü '*type1*'hedef makine türü ile çakışıyor'*type2*'

## <a name="remarks"></a>Açıklamalar

Girdi olarak belirtilen nesneyi dosyalar için farklı bir bilgisayara türleri derlendi.

Bağlantı çalışırsanız, örneğin, bir nesne ile derlenmiş dosyası **/CLR** ve bir nesne dosyası ile derlenmiş **/CLR: Saf** (makine türü CEE), bağlayıcı hatası LNK1112 oluşturacaktır. **/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Benzer şekilde, bir modülü ile oluşturursanız [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] derleyici ve x86 sahip başka bir modül derleyici ve bunları bağlamak için try bağlayıcı LNK1112 oluşturur.

Bu hatanın olası bir neden, 64 bitlik bir uygulama geliştirme ancak Visual C++ 64 bit derleyicileri birini yüklemediyseniz ' dir. Bu durumda, 64-bit yapılandırmaları kullanılabilir olmaz. Bu sorunu düzeltmek için Visual Studio için yükleyiciyi çalıştırın ve eksik C++ bileşenlerini yükleyin.

Değiştirirseniz bu hata ayrıca oluşabilir **etkin çözüm yapılandırması** içinde **Configuration Manager** ve Ara proje dosyalarını silmeden önce projeyi derlemek deneyin. Bu hatayı gidermek için seçin **çözümü yeniden derle** gelen **yapı** menüsü. Öğesini de seçebilirsiniz **temiz çözüm** gelen **yapı** menüsüne ve ardından yapı çözümü.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Araçları Hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
