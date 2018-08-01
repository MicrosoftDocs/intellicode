---
title: IntelliCode extension for Visual Studio
ms.date: 08/01/2018
ms.prod: visual-studio-family
ms.technology: code-smarts
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
---
# IntelliCode extension for Visual Studio

You can [download an experimental extension](https://go.microsoft.com/fwlink/?linkid=872707) for Visual Studio 2017 version 15.7 and later. The extension currently provides:

- AI-enhanced IntelliSense for C# that predicts the most likely correct API for the developer to use, rather than just presenting an alphabetical list of members. It uses the developer's current code context and patterns to provide this dynamic list.

- Inference of code style and formatting conventions for C# that helps you keep your code consistent by dynamically creating an [.editorconfig file](/visualstudio/ide/create-portable-custom-editor-options) from your codebase to define coding styles and formats. These conventions allow Visual Studio to offer automatic style and format fixes to clean up your document. More details on this feature can be found in [this blog article](https://aka.ms/vsicec).

## FAQ

### Q. Why does EditorConfig inference prepend a 1 to the filename?

A known issue in Visual Studio extensibility causes a **1.** to be prepended to the .editorconfig filename when you create it by right-clicking and choosing **Add** > **New Item**. Files named in this way are not recognized by the editorconfig processor in Visual Studio. You can work around this issue by removing the **1** in the **Add New Item** dialog. This problem is fixed in Visual Studio 2017 version 15.8 preview 4.

### Q. I don't see my EditorConfig Conventions taking effect - why?

There are a couple of common reasons this problem can occur:

- In Visual Studio 2017 versions prior to 15.8 preview 3, you need to close and reopen all open documents to see the conventions in the EditorConfig file you create take effect. This issue is fixed in version 15.8 preview 3.

- Formatting conventions never show up in the **Error List** or as "squiggles" in your code. They can, however, be fixed using the new **Format Document** (**Ctrl**+**K**, **Ctrl**+**D**) command that's available in Visual Studio 2017 version 15.8 preview 3 and later.

### Q. Format Document is not fixing my style conventions - why?

There are a couple of common reasons this problem can occur:

- You may not be using Visual Studio 2017 version 15.8 preview 3 or later. You need this version to be able to use the extended **Format Document** command to perform additional code cleanup for the current document.

- You may not be opted in to style fixes. The extended capability of fixing convention-based issues capability in **Format Document** only covers a fixed set of issues. You can change which issues are fixed in **Tools** > **Options** under **Text Editor** > **C#** > **Code Style** > **Formatting** > **General** > **Format Document Settings (Experiment)**. The default settings don't fix some style conventions. You can opt in to these via **Tools** > **options**. For example, **Apply implicit/explicit type preferences** runs style rules about the use of `var`.

### Q. Which EditorConfig Conventions can Visual Studio IntelliCode infer?

At present this feature is experimental, so we don't support the full set of conventions documented in the [code style settings reference](/visualstudio/ide/editorconfig-code-style-settings-reference) yet. IntelliCode can currently infer the following [formatting](#formatting-conventions) and [style](#style-conventions) conventions.

#### Formatting conventions

- csharp_space_between_method_declaration_parameter_list_parentheses
- csharp_space_between_method_declaration_empty_parameter_list_parentheses
- csharp_space_between_method_call_name_and_opening_parenthesis
- csharp_space_between_method_call_parameter_list_parentheses
- csharp_space_between_method_call_empty_parameter_list_parentheses
- csharp_space_after_keywords_in_control_flow_statements
- csharp_space_between_parentheses
- csharp_space_after_cast
- csharp_space_after_colon_in_inheritance_clause
- csharp_space_before_colon_in_inheritance_clause
- csharp_space_around_binary_operators
- csharp_indent_switch_labels
- csharp_indent_case_contents
- csharp_indent_case_contents_when_block
- csharp_indent_labels
- csharp_preserve_single_line_blocks
- csharp_preserve_single_line_statements
- csharp_new_line_before_open_brace
- csharp_new_line_before_else
- csharp_new_line_before_catch
- csharp_new_line_before_finally
- csharp_new_line_before_members_in_object_initializers
- csharp_new_line_before_members_in_anonymous_types
- csharp_new_line_between_query_expression_clauses

#### Style Conventions

- csharp__new_line_before_catch
- csharp_new_line_before_else
- csharp_new_line_before_members_in_anonymous_types
- csharp_new_line_before_members_in_object_initializers
- csharp_new_line_before_finally_style
- csharp_new_line_between_query_expression_clauses
- csharp_prefer_braces_style
- csharp_preferred_modifier_order_style
- csharp_prefer_simple_default_expression
- csharp_preserve_single_line_blocks
- csharp_space_after_cast
- csharp_space_after_keywords_in_control_flow_statements
- csharp_space_between_method_call_parameter_list_parentheses
- csharp_space_between_method_declaration_parameter_list_parentheses
- csharp_space_between_parentheses
- csharp_style_expression_bodied_accessors
- csharp_style_expression_bodied_constructors
- csharp_style_expression_bodied_indexers
- csharp_style_expression_bodied_methods
- csharp_style_expression_bodied_operators
- csharp_style_expression_bodied_properties
- csharp_style_inlined_variable_declaration
- csharp_style_pattern_local_over_anonymous_function
- csharp_style_pattern_matching_over_as_with_null_check
- csharp_style_var_for_built_in_types
- csharp_style_var_when_type_is_apparent
- dotnet_sort_system_directives_first
- dotnet_style_explicit_tuple_names
- dotnet_style_object_initializer
- dotnet_style_predefined_type_for_locals_parameters_members
- dotnet_style_predefined_type_for_member_access
- dotnet_style_prefer_inferred_anonymous_type_member_names
- dotnet_style_qualification_for_event
- dotnet_style_qualification_for_field
- dotnet_style_qualification_for_method
- dotnet_style_qualification_for_property
- dotnet_style_require_accessibility_modifiers

### Q. <a name="whynointellisense"/> I can't see the IntelliCode suggestions in my C# editing experience. Can you help?

IntelliCode suggestions appear in the standard Visual Studio IntelliSense UI for C#. Extensions that override that UI prevent the IntelliCode "starred" suggestions from appearing at the top of the list. You can verify if extensions are causing this behavior by turning them off and then trying IntelliSense again.

If this doesn't solve the problem for you, please report your issue via the Visual Studio [Report a Problem](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) feature, and mention IntelliCode in your report.

### Q. Which version of Visual Studio do I need to run the Visual Studio IntelliCode extension?

The Visual Studio IntelliCode extension is supported on Visual Studio 2017 version 15.7 preview 5 and later (all SKUs). Installation of the extension halts with **This extension is not installable on any currently installed products** if you don't have the minimum required version installed.

## See also

- [IntelliCode general FAQ](faq.md)
- [IntelliCode extension for Visual Studio Code](intellicode-visual-studio-code.md)