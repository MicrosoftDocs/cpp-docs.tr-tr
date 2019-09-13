---
title: Bağlayıcı Araçları hatası LNK1352
description: Desteklenmeyen bölüm birleştirme denendiğinde bağlayıcı araçları hatası LNK1352 oluşur.
ms.date: 09/10/2019
f1_keywords:
- LNK1352
helpviewer_keywords:
- LNK1352
ms.openlocfilehash: 38f773bfd669529dfb1ada9c7bb59e6f0962c9c7
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70908384"
---
# <a name="linker-tools-error-lnk1352"></a>Bağlayıcı Araçları hatası LNK1352

> '*section_name_1*' ve '*section_name_2*' farklı bölümlerle birleştirilemez

## <a name="remarks"></a>Açıklamalar

Bağlayıcı, izin verilmeyen bir bölüm birleştirmesi algıladı, çünkü *section_name_1* ve *section_name_2* aynı bölüm ile birleştirilmelidir. Örneğin, bağlayıcı `.stls` bölümü `.tls` ve bölümü farklı bölümler halinde birleştirme girişimi algılarsa bu hata oluşur.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

Bu sorun için bağlayıcı komut satırındaki [/merge](../../build/reference/merge-combine-sections.md) seçeneğini işaretleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları Hataları ve Uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
