
## �� Usage Examples

### Basic 3D Scene

```tsx
import { Canvas } from '@react-three/fiber'
import { OrbitControls, Box } from '@react-three/drei'

function Scene() {
  return (
    <Canvas>
      <ambientLight intensity={0.5} />
      <pointLight position={[10, 10, 10]} />
      <Box position={[0, 0, 0]} />
      <OrbitControls />
    </Canvas>
  )
}
```

### Multiple Viewports

```tsx
import { View } from '@/components/canvas/View'

function App() {
  return (
    <div className="grid grid-cols-2 gap-4">
      <View className="h-96" orbit>
        <Box />
      </View>
      <View className="h-96">
        <Sphere />
      </View>
    </div>
  )
}
```

## �� Styling

This project uses **Tailwind CSS** for styling. All components are fully responsive and mobile-friendly.

### Custom Classes

```tsx
// Responsive 3D viewport
<View className="h-64 md:h-96 lg:h-[500px]" />

// Grid layout
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
  <View className="aspect-square" />
</div>
```

## 🔧 Configuration

### TypeScript

The project includes TypeScript with basic configuration. For stricter type checking, you can enable strict mode in `tsconfig.json`:

```json
{
  "compilerOptions": {
    "strict": true,
    "target": "es2017"
  }
}
```

### Tailwind CSS

Configure Tailwind in `tailwind.config.js`:

```js
module.exports = {
  content: [
    './app/**/*.{js,ts,jsx,tsx}',
    './src/**/*.{js,ts,jsx,tsx}',
  ],
  theme: {
    extend: {
      // Your custom theme
    },
  },
  plugins: [],
}
```

## �� Available Scripts

```bash
# Development
yarn dev          # Start development server
yarn build        # Build for production
yarn start        # Start production server

# Code Quality
yarn lint         # Run ESLint
yarn prettier     # Check Prettier formatting

# Analysis
yarn analyze      # Analyze bundle size
```

## 🎯 Key Components

### `<View>` Component

Creates a 3D viewport that tracks an HTML element:

```tsx
<View className="h-96" orbit>
  <Your3DContent />
</View>
```

Props:
- `orbit` - Enable orbit controls
- `className` - CSS classes for the container
- `children` - 3D content to render

### `<Common>` Component

Provides basic lighting and camera setup:

```tsx
<Common color="lightblue" />
```

Props:
- `color` - Background color (optional)

## 🚀 Deployment

### Vercel (Recommended)

1. Push your code to GitHub
2. Connect your repository to Vercel
3. Deploy automatically

### Other Platforms

```bash
# Build the project
yarn build

# The build output will be in the .next folder
# Deploy the .next folder to your hosting platform
```

## �� Customization

### Adding 3D Models

1. Place `.glb` or `.gltf` files in `public/`
2. Use `useGLTF` hook:

```tsx
import { useGLTF } from '@react-three/drei'

function Model() {
  const { scene } = useGLTF('/your-model.glb')
  return <primitive object={scene} />
}
```

### Styling Components

All components support Tailwind classes:

```tsx
<View className="rounded-lg shadow-xl border-2 border-blue-500">
  <Box className="hover:scale-110 transition-transform" />
</View>
```

## 🐛 Troubleshooting

### Common Issues

1. **TypeScript errors**: The project uses basic TypeScript configuration
2. **3D models not loading**: Check file paths and formats
3. **Performance issues**: Use `useFrame` efficiently and avoid unnecessary re-renders
4. **Styling not applied**: Ensure Tailwind CSS is properly configured

### Getting Help

- Check the [React Three Fiber documentation](https://docs.pmnd.rs/react-three-fiber)
- Visit the [Three.js documentation](https://threejs.org/docs)
- Open an issue on GitHub

## �� Learn More

- [React Three Fiber](https://docs.pmnd.rs/react-three-fiber) - Documentation
- [Three.js](https://threejs.org) - 3D library
- [Next.js](https://nextjs.org) - React framework
- [Tailwind CSS](https://tailwindcss.com) - CSS framework

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Happy coding! ��**

If you find this project helpful, please give it a ⭐ star!