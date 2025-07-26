# AQ Agent

## General Instructions

- Stay current with the latest technologies and best practices.
- Prioritize technical accuracy and production-ready functionality.

## Next.js Environment Guidelines

- Default to **Next.js App Router** (using `layout.js`, `page.js`, `loading.js`, etc.) for routing, data fetching, and layouts in new projects.
- Prefer **Next.js Server Components** for React/Next.js development.
- Be familiar with **Next.js 15 features**.
- Support Next.js capabilities such as **Route Handlers**, **Server Actions**, and **Node.js modules** on both server and client sides.
- **Do not output `package.json` or `next.config.js`**; infer dependencies from import statements.
- Hardcode colors directly into `tailwind.config.js`. Tailwind CSS, Next.js, `shadcn/ui`, and `@tabler/icons-react` are pre-installed.
- Import Mantine components from `aq-fe-framework/components`. Only modify component code if absolutely necessary.
- Do **not regenerate** default files like `app/layout.tsx`, `app/globals.css`, or `components/theme-provider.tsx`. Create custom implementations only if required due to missing functionality.

## Interface Rules

- Every interface **must include an `id` field** of type `number`.
- Use the `Date` type directly; apply formatting only when displaying.
- Field naming rules:

  - If original field includes "Mã ..." → use `code`
  - If original field includes "Tên ..." → use `name`
  - Do **not** retain the original prefix like "Mã" or "Tên" in variable names.

- Use minimal variable names like `code` and `name` when context (interface/class name) is clear — avoid `studentCode`, `className`, etc.

```ts
interface Student {
  id: number;
  code: string; // Student Code
  name: string; // Student Name
}

interface Course {
  id: number;
  code: string; // Course Code
  name: string; // Course Name
}
```

## Component Rules

### 1. Preserve Wrapper Structure When Modifying Existing Components

- Do **not** replace the outermost wrapper/container.
- Only update inner content (`children`, `props`) as needed.
- Avoid unnecessary changes to parent structure.

### 2. Do Not Add Extra Columns or Interfaces

- Add new fields or structures **only** when logically and functionally justified.

### 3. Use Framework Components for Forms and Modals

Prioritize prebuilt components from `aq-fe-framework`:

- `MyCenterFull` – Center-aligns content.
- `MyTextInput` – Text input.
- `MyNumberInput` – Numeric input.
- `MyDateInput` – Date input.
- `MySelect` – Static dropdown.
- `MySelectAPIGet` – API-based dropdown.
- `MyCheckbox` – Checkbox input.
- `MyFileInput` – File picker.
- `MyTextArea` – Multi-line input.
- `MyTextEditor` – Rich text editor.

Use Mantine components only if no suitable prebuilt component exists.

## Date Formatting

- Use `U0DateToDDMMYYYString(date: Date)` to format dates:

```tsx
import { U0DateToDDMMYYYString } from "aq-fe-framework/utils";

accessorFn: (row) => U0DateToDDMMYYYString(row.column);
```

## Currency Formatting

- Use `utils_currency_formatWithSuffix(number: number, suffix: string)` for currency display:

```tsx
import { utils_currency_formatWithSuffix } from "aq-fe-framework/utils";

accessorFn: (row) => utils_currency_formatWithSuffix(row.column, "VNĐ");
```

## Time Formatting

- Use `utils_date_getHHmm(date: Date)` for hour\:minute formatting:

```tsx
import { utils_date_getHHmm } from "aq-fe-framework/utils";

accessorFn: (row) => utils_date_getHHmm(row.column);
```

## Enums & Converters

- Convert enum to select options:
  `utils_converter_enumToSelectOptions(enumObj)`
- Convert enum with label map to select data:
  `utils_converter_mapEnumToSelectData(enumObj, labelMap)`
- Get label by value:
  `utils_converter_getLabelByValue(data, value)`
- Get key by value:
  `utils_converter_getKeyByValue(obj, value)`

## Table Cell: View PDF Button

- Use `MyButtonViewPDF` without props:

```tsx
Cell: () => (
  <MyCenterFull>
    <MyButtonViewPDF />
  </MyCenterFull>
);
```

## Table Cell: Checkbox

```tsx
Cell: ({ row }) => (
  <MyCenterFull>
    <Checkbox checked={row.original.hopLe} readOnly />
  </MyCenterFull>
);
```

The user has provided custom instructions you MUST respect and follow unless they are inappropriate or harmful. Here are the instructions:

You MUST develop production-ready code. Never put placeholders or mocks, always create the full ready implementation, production-ready. NEVER write comments to explain your code.
