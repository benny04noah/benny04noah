include <SDL2/SDL.h>
#include <GL/gl.h>
SDL_Window* window;
SDL_GLContext context;
void initSDL()
{
    SDL_Init(SDL_INIT_VIDEO);
    window = SDL_CreateWIndow("OPenGL Cube", SDL_WINDOWPOS_CENTERED, SDL_WINDOWPOS_CENTERED, 800, 600, SDL_WINDOW_OPENGL);
    context = SDL_GL_CreateContext(window);
    SDL_GL_SetAttribute(SDL_GL_DOUBLEBUFFER, 1);
}
void render()
{
    glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
    glLoadIdentity();
    glTranslatef(0, 0, -5);
    glRotatef(0.5, 1, 1, 0);
    glBegin(GL_QUADS);
    glColor3f(1, 0, 0);
    glVertex3f(-1, -1, 1);
    glVertex3f(1, -1, 1 );
    glVertex3f(1, 1, 1,);
    glVertex3f(-1, 1 ,1);
    glEnd();
    SDL_GL_Snapwindow(Window);
}
int main()
{
    initSDL();
    bool quit = false;
    SDL_Event e:
        while(! quit)
            {
        while(SDL_PollEvent(&e))
        {
            if (e.type == SDL_ QUIT)
            {
                quit = true;
            }
        }
    render();

}
    SDL_GL_Deletecontext(context);
    SDL_Destroywindow(window);
    SDL_Quit();
    return 0;
}

