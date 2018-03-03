---
title: "Kaynak Derleyicisi önemli hatası RC1020 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1020
dev_langs:
- C++
helpviewer_keywords:
- RC1020
ms.assetid: 3e073ebf-9136-4bf8-ac6a-3c642ed64594
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db0806f85ae3dec2e75de4dbae4a084c3a3bb7a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1020"></a>Kaynak Derleyicisi Önemli Hatası RC1020
Beklenmeyen '#endif'  
  
 Bir `#endif` yönergesi görünen eşleşen olmadan `#if`, **#ifdef**, veya **#ifndef** yönergesi.  
  
 Bir eşleme olduğundan emin olun `#endif` her `#if`, **#ifdef**, ve **#ifndef** deyimi.